# Домашнее задание к занятию `"Установка Kubernetes"` - `Сулименков Алексей`

### Цель задания

Установить кластер K8s.

### Чеклист готовности к домашнему заданию

1. Развёрнутые ВМ с ОС Ubuntu 20.04-lts.

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. [Инструкция по установке kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/).
2. [Документация kubespray](https://kubespray.io/).

---

### Задание 1. Установить кластер k8s с 1 master node

1. Подготовка работы кластера из 5 нод: 1 мастер и 4 рабочие ноды.
2. В качестве CRI — containerd.
3. Запуск etcd производить на мастере.
4. Способ установки выбрать самостоятельно.

---

### Ответ

Из-за ограниченности ресурсов будет 1 master и 3 worker нод, устанавиливался черезе [kubeadm](https://kubernetes.io/docs/reference/setup-tools/kubeadm/ "kubeadm") . В качестве CNI плагина использовался [cilium](https://cilium.io "cilium") с маршрутизацией BGP. В качестве SC - [Linstor](https://piraeus.io "Linstor") .

<details> <summary>kubectl get node</summary>

![kubectl get node](https://github.com/biparasite/kuber-homeworks-07/blob/main/task_1.1.png "kubectl get node")

</details>

<details> <summary>cilium status</summary>

![cilium status](https://github.com/biparasite/kuber-homeworks-07/blob/main/task_1.2.png "cilium status")

</details>

<details> <summary>kubectl get pod -A</summary>

![kubectl get pod -A](https://github.com/biparasite/kuber-homeworks-07/blob/main/task_1.3.png "kubectl get pod -A")

</details>

---

### Правила приёма работы

1. Домашняя работа оформляется в своем Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд `kubectl get nodes`, а также скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.
