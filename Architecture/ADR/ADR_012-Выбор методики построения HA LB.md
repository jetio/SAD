# Выбор методики построения HA Load Balancing

## Status (Статус)
DONE

## Context (Условия)
Необходимо выбрать технологию высокодоступной балансировки для backend-компонентов и систем.

## Decision (Решение)
Будем использовать связку NGINX + Keepalived + VRRP для HTTP и HAproxy + Keepalived + VRRP для остальных протоколов. 

## Consequences (Последствия)
Получим стандартизованный и широко поддерживаемый подход к организации HA LB.

## Metainformation (Заметки)
* (Achieving High Availability with HAProxy and Keepalived: Building a Redundant Load Balancer)[https://sysadmins.co.za/achieving-high-availability-with-haproxy-and-keepalived-building-a-redundant-load-balancer/]
* (HA of Haproxy - Using Keepalived VRRP)[https://accelazh.github.io/loadbalance/HA-Of-Haproxy-Using-Keepalived-VRRP]
* (NGINX. High Availability)[https://www.nginx.com/products/nginx/high-availability/]

## Measurements (Измерения)
N/A
