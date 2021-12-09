# Laboratoire 4 - Docker

> Auteurs: Gwendoline Dössegger, Noémie Plancherel, Gaby Roch
>
> Date: 12 janvier 2021
>
> Dépôt Git: https://github.com/g-roch/heig-ait-lab04

[TOC]

## 1. Introduction

## 2. Tâches

### Tâche 0

> [M1] Do you think we can use the current solution for a production environment? What are the main problems when deploying it in a production environment?

Non, notre environnement n'est pas scalable. Nous ne pouvons pas ajouter dynamiquement de nouveaux noeuds à notre infrastructure. On est obligé d'avoir des employés afin de déployer l'application car on ne peut pas le faire automatiquement.

> [M2] Describe what you need to do to add new `webapp` container to the infrastructure. Give the exact steps of what you have to do without modifiying the way the things are done. Hint: You probably have to modify some configuration and script files in a Docker image.

-> haproxy configuration fichier afin d'ajouter le nouveau noeud

-> modifier docker-compose pour build une webapp supplémentaire et le lier au haproxy

-> rebuild et relancer tous les containers avec un docker-compose build puis un docker-compose up -d (arrière plan) 

> [M3] Based on your previous answers, you have detected some issues in the current solution. Now propose a better approach at a high level.

-> avoir une détection de la charge sur HAProxy qui lance une commande pour déployer des noeuds supplémentaires

-> avoir une commande pour avoir des noeuds supplémentaires, modifier la config HAProxy et relancer les noeuds supplémentaires

> [M4] You probably noticed that the list of web application nodes is hardcoded in the load balancer configuration. How can we manage the web app nodes in a more dynamic fashion?

-> modifier la config de HAProxy pour qu'elle détecte automatiquement la présence de nouveau noeuds.

> [M5] Do you think our current solution is able to run additional management processes beside the main web server / load balancer process in a container? If no, what is missing / required to reach the goal? If yes, how to proceed to run for example a log forwarding process?



> [M6] What happens if we add more web server nodes? Do you think it is really dynamic? It's far away from being a dynamic configuration. Can you propose a solution to solve this?



### Tâche 1

## 3. Difficultés

## 4. Conclusion