---
type: rule
archivedreason: 
title: Schema - Do you have standard Tables and Columns?
guid: 0a8b7eec-9b71-478b-b90e-6af7ac64df27
uri: have-standard-tables-and-columns
created: 2019-11-05T22:52:15.0000000Z
authors:
- title: Adam Cogan
  url: https://ssw.com.au/people/adam-cogan
related: []
redirects:
- schema-do-you-have-standard-tables-and-columns

---


1.&#160;All tables should have the following fields&#58;<br><div><table cellspacing="0" width="100%" class="ssw15-rteTable-default"><tbody><tr><td class="ssw15-rteTable-default" style="width&#58;50%;"><strong>Field</strong></td><td class="ssw15-rteTable-default" style="width&#58;50%;"><strong>SQL Server Field Properties</strong></td></tr><tr><td class="ssw15-rteTable-default">CreatedUtc</td><td class="ssw15-rteTable-default">datetime2 Allow Nulls=False Default=GETUTCDATE()</td></tr><tr><td class="ssw15-rteTable-default">CreatedUserId</td><td class="ssw15-rteTable-default">Foreign Key to Users table, Allow Nulls=False</td></tr><tr><td class="ssw15-rteTable-default">ModifiedUtc</td><td class="ssw15-rteTable-default">datetime2 Allow Nulls=False Default=GETUTCDATE()</td></tr><tr><td class="ssw15-rteTable-default">ModifiedUserId</td><td class="ssw15-rteTable-default">Foreign Key to Users table, Allow Nulls=False</td></tr><tr><td class="ssw15-rteTable-default">Concurrency</td><td class="ssw15-rteTable-default">rowversion Allow Nulls=Falsev<br></td></tr></tbody></table><br></div>
<br><excerpt class='endintro'></excerpt><br>
<p>​The first three are examples of bad table records. The last one is an example of how this table structure should be entered.<br>
</p><dl class="image"><dt><img src="/PublishingImages/imgGoodBadPracticesExampleSQLFields.png" alt="imgGoodBadPracticesExampleSQLFields.png" style="width&#58;750px;height&#58;121px;" /></dt><dd>Figure&#58; 3 bad examples and 1 good example of Row auditing</dd></dl>​
<p>
   <b>Note #1&#58;</b> Never set the CreatedUtc field - instead use a default GETUTCDATE()<br><b>Note #2&#58;</b> These fields offer basic row auditing that will cover the majority of applications. When an application has specific auditing&#160;requirements, they should be analysed to see if this approach is sufficient.</p><p>2. All databases should have a table with one record to store application Defaults. This table should be called 'Control'.<br>If the settings are not application-wide, but just for that user then an XML (do not use an INI file) for simple stuff might be better. Examples are saving the 'User' for logon, 'Select Date Range' for a report, form positions, etc.</p><p>.NET programs have an Application.Configuration which exports to XML file (app.config) automatically. It works very well, and deployment is very simple. It's integrated right into the Visual Studio.NET designer as well.<br><br>3. All databases should have a version table to record structural changes to tables. See&#160;SSW Rules to Better Code<br>&#160;<br>4. Lookup tables that have just two columns should be consistent and follow this convention&#58; CategoryId (int) and CategoryName (varchar(100)).</p><p>The benefit is that a generic lookup form can be used. You will just need the generic lookup form pass in the TableName and Column1 and Column2.</p><p>
   <b>Note #3&#58;</b> The problem with the naming is the primary keys don't match<br><b>Note #4&#58;</b> The benefit with the character primary key columns is that queries and query strings have meaning Eg.&#160;http&#58;//www.ssw.com.au/ssw/Download/Download.aspx?GroupCategoryID=5BUS&#160;from this URL I can guess that it is in the business category.<br></p>

