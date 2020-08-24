# magento2-exactmatch

In Magento 2 releases up to at least 2.3.5, no native option for exact match search queries did exist.

This extensions overwrites the Match class, where the FULLTEXT search with MATCH...AGAINST happens.

While it was possible to require a match for all words a customer searched for, it was not possible
to match the complete string that was entered.

For example, the search term "women t-shirt blue" did not end up as this string. Magento 2 uses these words
to create a match query. When the match option is set to "must" (using search_request.xml), it looks like this:

+women +t-shirt +blue

In a lot of cases, that might work. There are situations however, where that condition doesn't match a product name
which could be "amazing women t-shirt blue". 

This extension fixes just that and treats the input query as an exact match query, based on the MySQL FULLTEXT search.

For more information see the BOOLEAN MODE documentation of MySQL:

https://dev.mysql.com/doc/refman/8.0/en/fulltext-boolean.html


Also see, https://janbrinkmann.de - you can hire me for Magento, Shopware and Symfony development :-)

