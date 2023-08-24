- [values.yaml](https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/values.yaml) - параметры компонентов %%vmsingle, vmagent, vmalert, vmalertmanager%%

- [vmalertmanager-config.yaml](https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/vmalertmanager-config.yaml) - параметры route/receivers для alertmanager

- [vmagent-relabel-config.yaml](https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/vmagent-relabel-config.yaml) - дополнительные параметры релейблинга для vmagent (можно отключить в values)

- [vmrule.yaml](https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/vmrule.yaml) - набор правил алертинга (можно отключить в values)

- [vmstaticscrape.yaml](https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/vmstaticscrape.yaml) - конфиги скейпинга метрик системных компонентов k8s (можно отключить в values)

- [prometheusrule.yaml](https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/prometheusrule.yaml) - дополнительные правила (тип: records) для алертинга и мониторинга (можно отключить в values)

Настройки образов задаются через параметры [victoria-metrics-operator](https://gitlab.sirius.online/infra/victoria-metrics-operator/-/blob/main/chart/values.yaml) в блоке `env:`

Сервисы для всех приложений из стека Виктории создаются с помощью параметров victoria-metrics-operator.

Ингрессы для vmagent и vmalertmanager создаются из шаблонов и параметров чарта victoria-metrics-stack.

victoria-metrics-operator следит за изменениями в настройках приложений стека и выполняет автоматическое применение новых параметров.