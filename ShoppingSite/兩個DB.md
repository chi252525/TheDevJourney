
```java


import java.util.HashMap;
import java.util.Map;
import java.util.Objects;
import javax.sql.DataSource;
import org.apache.commons.dbcp2.BasicDataSource;
import org.springframework.beans.factory.annotation.Qualifier;
import org.springframework.boot.context.properties.ConfigurationProperties;
import org.springframework.boot.jdbc.DataSourceBuilder;
import org.springframework.boot.orm.jpa.EntityManagerFactoryBuilder;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.data.jpa.repository.config.EnableJpaRepositories;
import org.springframework.jdbc.core.JdbcTemplate;
import org.springframework.orm.jpa.JpaTransactionManager;
import org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean;
import org.springframework.transaction.PlatformTransactionManager;
import org.springframework.transaction.annotation.EnableTransactionManagement;

@Configuration
@EnableTransactionManagement
@EnableJpaRepositories(
    basePackages = {
      NcbizModuleDbJpaRepositoryConfiguration.IMB_DAO_PACKAGE,
    },
    entityManagerFactoryRef = "imbEntityManagerFactory",
    transactionManagerRef = "imbTransactionManager")
public class NcbizModuleDbJpaRepositoryConfiguration {

  public static final String IMB_ENTITY_PACKAGE =
      "tw.com..ap12.infra.dataprovider.entity.ncbizmoduledb";

  public static final String IMB_DAO_PACKAGE =
      "tw.com..ap12.infra.dataprovider.dao.ncbizmoduledb";

  @ConfigurationProperties(prefix = "imb.spring.datasource")
  @Bean(name = "imbDataSource", destroyMethod = "")
  public DataSource imbDataSource() {
    return DataSourceBuilder.create().type(BasicDataSource.class).build();
  }

  @Bean(name = "imbEntityManagerFactory")
  public LocalContainerEntityManagerFactoryBean imbEntityManagerFactory(
      EntityManagerFactoryBuilder builder, @Qualifier("imbDataSource") DataSource dataSource) {

    Map<String, Object> properties = new HashMap<>();
    properties.put("hibernate.physical_naming_strategy", BigCamelNamingStrategy.class);

    return builder
        .dataSource(dataSource)
        .packages(IMB_ENTITY_PACKAGE)
        .properties(properties)
        .persistenceUnit("default")
        .build();
  }

  @Bean(name = "imbTransactionManager")
  public PlatformTransactionManager imbTransactionManager(
      @Qualifier("imbEntityManagerFactory")
          LocalContainerEntityManagerFactoryBean entityManagerFactory) {
    return new JpaTransactionManager(Objects.requireNonNull(entityManagerFactory.getObject()));
  }

  @Bean(name = "imbJdbcTemplate")
  public JdbcTemplate imbTemplate(@Qualifier("imbDataSource") DataSource dataSource) {
    return new JdbcTemplate(dataSource);
  }
}
```