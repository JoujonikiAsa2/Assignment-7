### Question: 1. What is PostgreSQL?

**_Ans:_** &nbsp; PostgreSQL একটি উন্নত ওপেন সোর্স রিলেশনাল ডেটাবেস ম্যানেজমেন্ট সিস্টেম।

### Question: 2. What is the purpose of a database schema in PostgreSQL?

**_Ans:_** &nbsp; ডেটাবেজ স্কিমা যে কোন ধরণের গঠন প্রদর্শন করে যা আমরা ডেটার সাথে সংজ্ঞায়িত করি, যেমন টেবিল, ফিল্ড, ভিউ, ফাংশন, রিলেশন, ইন্ডেক্স। PostgreSQL এ এই ডেটাবেজ স্কিমার উদ্দেশ্য ডেটাবেজের ডেটাগুলিকে অরগানাইজ করা, সিকিউরিটি বাড়ানো এবং ম্যানেজ করা।

### Question: 3. Explain the Primary Key and Foreign Key concepts in PostgreSQL.

**_Ans:_** &nbsp; Primary key হচ্ছে কলাম বা কলাম সমষ্টি যা কখনোই NULL বা duplicate হতে পারেনা। এটি টেবিলের row এর ডেটাকে unique ভাবে identify করে। Foreign key হচ্ছে কলাম বা কলাম সমষ্টি যা অন্য টেবিলের primary key কে রেফার করে।

### Question: 4. What is the difference between the VARCHAR and CHAR data types?

**_Ans:_** &nbsp; VARCHAR এবং CHAR এর মধ্যে পার্থক্য হচ্ছে storage এবং behavior এ। VARCHAR শুধুমাত্র প্রয়োজনীয় storage নেয় । CHAR এ string যদি ছোট হয়ে নির্ধারিত জায়গার তুলনায় তাহলে অতিরিক্ত জায়গা space দিয়ে পুর্ণ রাখে।

### Question: 5. Explain the purpose of the WHERE clause in a SELECT statement.

**_Ans:_** &nbsp; SELECT statement এ WHERE clause ব্যবহার করার উদ্দেশ্য হচ্ছে নির্দিষ্ট শর্ত দিয়ে ডেটা ফিল্টার করা;

### Question: 6. What are the LIMIT and OFFSET clauses used for?

**_Ans:_** &nbsp; LIMIT নির্দিষ্ট সংখ্যক row কে রিটার্ন করে। এবং নির্দিষ্ট সংখ্যক row বাদ দিয়ে পরের row গুলিকে রিটার্ন করে

### Question: 7. How can you modify data using UPDATE statements?

**_Ans:_** &nbsp; UPDATE statement এর দ্বারা ডেটাকে পরিবর্তন করার জন্য আমাদের SET এবং WHERE clause এর প্রয়োজন।
Table name: user_info</br>

<pre>
+---------------------------------+</br>
|id    |name   |age   |country    |</br>
+-------+------+------------------+</br>
|1     |Asa    |25    |Bangladesh |</br>
-----------------------------------</br>
|2     |Nisa   |24    |Nepal      |</br>
-----------------------------------</br>
</pre>

উদাহরণঃ</br>

<pre>
UPDATE user_info (টেবিলের নাম দিতে হবে)</br>
SET name = 'Joujoniki Asa Roy' (এখানে যে কলামের পরিবর্তন করতে চাই সে কলামের নাম ও ভ্যালু দিতে হবে)</br>
WHERE id = 1; (কোন শর্ত সাপেক্ষে পরিবর্তন করতে চাই তা WHERE clause এর মধ্যে লিখতে হবে)</br>
</pre>

### Question: 8. What is the significance of the JOIN operation, and how does it work in PostgreSQL?

**_Ans:_** &nbsp; JOIN operation দিয়ে মুলত একাধিক টেবিলের সাথে সম্পর্ক স্থাপন করা যায়। PostgreSQL এ JOIN operation মধ্যমে সেই টেবিল গুলতে মিল থাকা ডেটা গুলিকে দেখানো হয়।

### Question: 9. Explain the GROUP BY clause and its role in aggregation operations.

**_Ans:_** &nbsp; GROUP BY clause টি একই ধরনের মানের ডেটাগুলিকে একটি সমষ্টি তৈরি করে। MIN(), MAX(), COUNT(), SUM(), and AVG() এই সকল Aggregation operation এর সাথে ব্যবহৃত হয়।

### Question: 10. How can you calculate aggregate functions like COUNT(), SUM(), and AVG() in PostgreSQL?

**_Ans:_** &nbsp;
**_COUNT():_** একটি টেবিলে মোট কতটি রেকর্ড আছে তা রিটার্ন করে।</br>
**_SUM():_** একটি টেবিলের নির্দিষ্ট কলামের মান গুলো যোগ করে রিটার্ন করে;</br>
**_AVG():_** একটি টেবিলের নির্দিষ্ট কলামের মান গুলো যোগ করে মো্ট রেকর্ড সংখ্যা দিয়ে ভাগ করে একটি মান রিটার্ন করে।</br>

উদাহরণঃ
Table name: user_info </br>

<pre>
+-----------------------------------------------+ </br>
|id   |name |age |daily_income |country         | </br>
+-------+------+--------------------------------+ </br>
|1    |Asa  |25  |1200         |Bangladesh      | </br>
------------------------------------------------- </br>
|2    |Nisa |24  |1000         |Nepal           | </br>
------------------------------------------------- </br>
</pre>

<pre>
**_COUNT():_** </br>
SELECT COUNT(\*) as total_user FROM user_info;</br>
**_SUM():_** </br>
SELECT SUM(daily_income) as total_income FROM user_info;</br>
**_AVG():_** </br>
SELECT AVG(daily_income) as avg_income from user_info;</br>
</pre>
