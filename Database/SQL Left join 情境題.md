

1.情境

```sql
select * from ec_chat_history ch
left join ec_chat_shopper cs
on ch.chat_user_id = cs.chat_user_id
left join ec_chat_channel cc
on cc.chat_shopper_id =cs.id where ch.shop_url ='XXX';
```
單表獨立：ec_chat_history

一對多：ec_chat_shopper       ec_chat_channel

## 2.錯誤訊息

N/A

## 3.問題點

會拉到重複的資料

## 4.解決方法
```sql
select * from ec_chat_history ch
left join ec_chat_channel cc
on cc.document_id =ch.chat_channel_document_id where ch.shop_url ='XXX';
```