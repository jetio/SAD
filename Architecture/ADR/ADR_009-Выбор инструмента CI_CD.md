# Выбор инструмента CI/CD

## Status (Статус)
DONE

## Context (Условия)
Альтернативы:
* GitLab + Jenkins
* GitLab + ArgoCD

## Decision (Решение)
Будем использовать GitLab + ArgoCD, как OpenSource-решение, предназначенное для GitOps (единый GitOps-оператор) и автоматизации развертывания на платформе Kubernetes 

## Consequences (Последствия)
Стандартизируем подход к раскатке на DEV-QA-STAGE-PROD окружениях. Получим инструмент управления политиками раскатки для мультисервисных решений.

## Metainformation (Заметки)
*(GitOps)[[https://habr.com/ru/articles/700760/](https://habr.com/ru/companies/oleg-bunin/articles/690544/)]
*(Choosing deployment tool)[https://dev.to/pavankulkarni/choosing-the-right-deployment-tool-argocd-or-jenkins-jenkins-argocd-2cen]

## Measurements (Измерения)
N/A
