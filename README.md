# Домашнее задание к занятию "3.5. Файловые системы"

1. Узнайте о sparse (разряженных) файлах.

`Изучил`

2. Могут ли файлы, являющиеся жесткой ссылкой на один объект, иметь разные права доступа и владельца? Почему? 

`Нет не могут , т.к. хардлинки все ссылаются на один и тот же блок памяти на жестком диске , по сути являясь копией друг друга`

3. Сделайте vagrant destroy на имеющийся инстанс Ubuntu. Замените содержимое Vagrantfile следующим:

![image](https://user-images.githubusercontent.com/106814458/178355669-07bf0cba-c0bc-4a4a-9697-f5a24a2d366c.png)



4. Используя fdisk, разбейте первый диск на 2 раздела: 2 Гб, оставшееся пространство.

![image](https://user-images.githubusercontent.com/106814458/178358210-472904ce-27ea-4c38-a13c-6d16da2d0f86.png)


5. Используя sfdisk, перенесите данную таблицу разделов на второй диск.

![image](https://user-images.githubusercontent.com/106814458/178358769-82a011d0-b4d6-475c-87be-22b7de869d45.png)

6. Соберите mdadm RAID1 на паре разделов 2 Гб. 

![image](https://user-images.githubusercontent.com/106814458/178369669-5fc60fdf-89e0-458c-9f4e-135b08ae7c64.png)

7. Соберите mdadm RAID0 на второй паре маленьких разделов.

![image](https://user-images.githubusercontent.com/106814458/178369825-3aac4493-3077-40c8-aa68-46b601c24dc3.png)

8. Создайте 2 независимых PV на получившихся md-устройствах.

![image](https://user-images.githubusercontent.com/106814458/178498481-96ce12f6-1c63-498e-89ed-bdd0bb325ba7.png)

9. Создайте общую volume-group на этих двух PV.

![image](https://user-images.githubusercontent.com/106814458/178498597-f8a8da33-2ed3-4894-836e-196e076b7e1f.png)

10. Создайте LV размером 100 Мб, указав его расположение на PV с RAID0.

![image](https://user-images.githubusercontent.com/106814458/178499452-1032a521-ff90-42ba-8ab8-3d11c4bfa3ae.png)

11. Создайте mkfs.ext4 ФС на получившемся LV.

![image](https://user-images.githubusercontent.com/106814458/178499593-2c5da88e-f627-4b24-861d-a679abfea454.png)

12. Смонтируйте этот раздел в любую директорию, например, /tmp/new.

![image](https://user-images.githubusercontent.com/106814458/178499868-104232ce-0cdd-405f-832d-0e52dfdc828b.png)

13. Поместите туда тестовый файл, например wget https://mirror.yandex.ru/ubuntu/ls-lR.gz -O /tmp/new/test.gz.

![image](https://user-images.githubusercontent.com/106814458/178500125-f2ef314e-bdbb-40ac-80ee-71f8ed89c0bf.png)

14. Прикрепите вывод lsblk.

![image](https://user-images.githubusercontent.com/106814458/178500230-6d66e9fc-bbb5-4f1f-8d68-3ea313b4a9b2.png)

15. Протестируйте целостность файла:

![image](https://user-images.githubusercontent.com/106814458/178500408-ba6fcf02-26fd-48fa-a3bb-602952d9b903.png)

16. Используя pvmove, переместите содержимое PV с RAID0 на RAID1.

![image](https://user-images.githubusercontent.com/106814458/178500749-97ec7abc-e708-491f-8c99-20f504651ab2.png)

17. Сделайте --fail на устройство в вашем RAID1 md.

![image](https://user-images.githubusercontent.com/106814458/178501419-fe763e2c-6b0c-4a3a-9756-5a3d64a5c328.png)

18. Подтвердите выводом dmesg, что RAID1 работает в деградированном состоянии.

![image](https://user-images.githubusercontent.com/106814458/178501550-348f3d8c-65f4-4dac-8bb5-1cafe8852d26.png)

19. Протестируйте целостность файла, несмотря на "сбойный" диск он должен продолжать быть доступен:

![image](https://user-images.githubusercontent.com/106814458/178501654-5c46222b-3f93-4ef4-8ea5-4637a1511304.png)

20. Погасите тестовый хост, vagrant destroy.

![image](https://user-images.githubusercontent.com/106814458/178501864-06d8c9c6-9cdf-41b2-80f1-c3eae312cc48.png)







