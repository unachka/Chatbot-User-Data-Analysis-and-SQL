## Chatbot-User-Data-Analysis

### **Tools used :** <br> <sub> <span style="color:blue; font-size:4em;">BigQuery BigQuery SQL, Google Data Studio, and GoogleSheet</span>
  
<br>
  
  
  
```ruby
### Create a table with all CatchAll content using Big Query/SQL 

SELECT
  original.content,
  original.external_id, 
  original.inserted_at
FROM (
  SELECT
    catchall.in_reply_to,
    catchall.faq_uuid
  FROM
    `dimagi-*****-chatbot-*****.*******.messages` AS catchall
  WHERE
    catchall.faq_uuid IN ('*****-***-123459-#####-*****','*****-***-23456-#####-*****',
                          '*****-***-5678901-#####-*****')) catchall
LEFT JOIN
  `dimagi-*****-chatbot-*****.*******.messages` AS original
ON
  catchall.in_reply_to = original.external_id;
```


![Page1](/images_1/page1.png)
![Page1](/images_1/page2.png)



