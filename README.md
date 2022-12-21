# Hibernate-one-to-many

- Bu projede Hibernate ile One-to-Many (Bi-Directional) uygulaması yapılmıştır

- Veritabanına Tablolar tanımlanmıştır.
- Kurs sınıfı Olusturulup eğitmen sınıfı güncellenmiştir.

- Bu kursta cascade(basamaklandırma) yönteminden silme işlemi kaldırılmıştır.

- Instructor bilgileri korunup course bilgieri silinmiştir

  ```
  CREATE TABLE `instructor_detail` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `youtube_channel` varchar(128) DEFAULT NULL,
  `hobby` varchar(45) DEFAULT NULL,
  PRIMARY KEY (`id`)
  ) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=latin1;

  CREATE TABLE `instructor` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `first_name` varchar(45) DEFAULT NULL,
  `last_name` varchar(45) DEFAULT NULL,
  `email` varchar(45) DEFAULT NULL,
  `instructor_detail_id` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `FK_DETAIL_idx` (`instructor_detail_id`),
  CONSTRAINT `FK_DETAIL` FOREIGN KEY (`instructor_detail_id`)
  REFERENCES `instructor_detail` (`id`) ON DELETE NO ACTION ON UPDATE NO ACTION
  )ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=latin1;
  ```
