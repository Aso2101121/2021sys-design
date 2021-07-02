//購入テーブル 

CREATE TABLE IF NOT EXISTS `d_purchase` ( 

  `order_id` bigint(20) NOT NULL AUTO_INCREMENT, 

  `customer_code` varchar(50) NOT NULL, 

  `purchase_date` date NOT NULL, 

  `total_price` int(11) NOT NULL, 

  PRIMARY KEY (`order_id`) 

) 

 

//購入テーブル詳細 

CREATE TABLE IF NOT EXISTS `d_purchase_detail` ( 

  `detail_id` bigint(20) NOT NULL AUTO_INCREMENT, 

  `order_id` bigint(20) NOT NULL DEFAULT '0', 

  `item_code` int(11) NOT NULL, 

  `price` int(11) NOT NULL, 

  `num` int(11) NOT NULL, 

  PRIMARY KEY (`detail_id`,`order_id`) 

) 

 

//ユーザー（顧客）テーブル 

CREATE TABLE IF NOT EXISTS `m_customers` ( 

  `customer_code` varchar(50) NOT NULL DEFAULT '', 

  `pass` varchar(50) NOT NULL, 

  `name` varchar(20) NOT NULL, 

  `address` varchar(100) NOT NULL, 

  `tel` varchar(20) NOT NULL, 

  `mail` varchar(100) NOT NULL, 

  `del_flag` int(1) DEFAULT NULL, 

  `reg_date` date NOT NULL, 

  PRIMARY KEY (`customer_code`) 

) 

//カテゴリテーブル 

CREATE TABLE IF NOT EXISTS `m_category` ( 

  `category_id` int(11) NOT NULL AUTO_INCREMENT, 

  `name` varchar(20) NOT NULL, 

  `reg_date` date NOT NULL, 

  PRIMARY KEY (`category_id`) 

) 

//商品テーブル 

CREATE TABLE IF NOT EXISTS `m_items` ( 

  `item_code` int(11) NOT NULL DEFAULT '0', 

  `item_name` varchar(50) NOT NULL, 

  `price` int(11) NOT NULL, 

  `category_id` int(11) NOT NULL, 

  `image` varchar(200) NOT NULL, 

  `detail` varchar(500) DEFAULT NULL, 

  `del_flag` int(11) DEFAULT NULL, 

  `reg_date` date NOT NULL, 

  PRIMARY KEY (`item_code`), 

  FOREIGN KEY PK_category(category_id) REFERENCES m_category(category_id) 

) 
