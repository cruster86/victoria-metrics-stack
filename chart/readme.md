- (https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/values.yaml)[values.yaml] - параметры компонентов %%vmsingle, vmagent, vmalert, vmalertmanager%%

- (https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/vmalertmanager-config.yaml)[vmalertmanager-config.yaml] - параметры route/receivers для alertmanager

- (https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/vmagent-relabel-config.yaml)[vmagent-relabel-config.yaml] - дополнительные параметры релейблинга для vmagent (можно отключить в values)

- (https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/vmrule.yaml)[vmrule.yaml] - набор правил алертинга (можно отключить в values)

- (https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/vmstaticscrape.yaml)[vmstaticscrape.yaml] - конфиги скейпинга метрик системных компонентов k8s (можно отключить в values)

- (https://gitlab.sirius.online/clusters/univ-prod/-/blob/main/helm/values/victoria-metrics-stack/prometheusrule.yaml)[prometheusrule.yaml] - дополнительные правила (тип: records) для алертинга и мониторинга (можно отключить в values)

Настройки образов задаются через параметры (https://gitlab.sirius.online/clusters/univ-prod/-/tree/main/helm/values/victoria-metrics-operator)[victoria-metrics-operator] в блоке `env:`

Сервисы для всех приложений из стека Виктории создаются с помощью victoria-metrics-operator.

Ингрессы для vmagent и vmalertmanager создаются из шаблонов и параметров чарта victoria-metrics-stack.