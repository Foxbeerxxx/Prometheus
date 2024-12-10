# Домашнее задание к занятию "`Система мониторинга Prometheus`" - `Татаринцев Алексей`


---

### Задание 1

`Установите Prometheus`

1. `Создаю пользователя Prometheus`
```
sudo useradd --no-create-home --shell /bin/false Prometheus
```
2. `Скачиваем Prometheus с github `
```
wget https://github.com/prometheus/prometheus/releases/download/v3.0.1/prometheus-3.0.1.darwin-amd64.tar.gz
```
3. `Распаковываю и копирую в пользовательскую директорию`
```
tar vxf prometheus*.tar.gz
cd prometheus*/
sudo mv prometheus /usr/local/bin
sudo mv promtool /usr/local/bin
sudo chown prometheus:prometheus /usr/local/bin/prometheus
sudo chown prometheus:prometheus /usr/local/bin/promtool
```
4. `Создаю новый файл службы для управления Prometheus`
```
nano /etc/systemd/system/prometheus.service
```
```
  GNU nano 4.8                /etc/systemd/system/prometheus.service                          
[Unit]
Description=Prometheus Service Netology Lesson 9.4 TatarincevA
After=network.target
[Service]
User=prometheus
Group=prometheus
Type=simple
ExecStart=/usr/local/bin/prometheus \
--config.file /etc/prometheus/prometheus.yml \
--storage.tsdb.path /var/lib/prometheus/ \
--web.console.templates=/etc/prometheus/consoles \
--web.console.libraries=/etc/prometheus/console_libraries
ExecReload=/bin/kill -HUP $MAINPID Restart=on-failure
[Install]
WantedBy=multi-user.target

```
5. `Создаю директорию для хранения данных`
```
sudo mkdir /var/lib/prometheus
sudo chown prometheus:prometheus /var/lib/prometheus

```

6. `Включаю Prometheus и вкючаю при перезагрузке`

```
sudo systemctl daemon-reload
sudo systemctl start prometheus
sudo systemctl enable prometheus

```

6. `Проверяю результат`

```
sudo systemctl status prometheus
```
![1](https://github.com/Foxbeerxxx/Prometheus/blob/main/img/img1.png)`

![2](https://github.com/Foxbeerxxx/Prometheus/blob/main/img/img2.png)`



`При необходимости прикрепитe сюда скриншоты
![Название скриншота 1](ссылка на скриншот 1)`


---

### Задание 2

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота 2](ссылка на скриншот 2)`


---

### Задание 3

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`

### Задание 4

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`
