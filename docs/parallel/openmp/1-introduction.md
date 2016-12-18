---
title: "1. Introduction | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1. Introduction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document spécifie une collection de directives de compilateur, de fonctions de bibliothèque, et de variables d'environnement qui peuvent être utilisées pour spécifier le parallélisme de mémoire partagée dans des programmes C et C\+\+.  Les fonctionnalités décrites dans ce document est collectivement appelé *l'interface de programmation d'applications OpenMP C\/C\+\+ \(API\)*.  L'objectif de cette spécification est de fournir un modèle pour la programmation parallèle qui permet à un programme pour être portable entre les architectures de mémoire partagée de fournisseurs différents.  L'API d'OpenMP C\/C\+\+ est prise en charge par les compilateurs de nombreux fournisseurs.  Plus d'informations sur OpenMP, y compris *l'interface de programmation d'applications OpenMP Fortran*, se trouvent au site Web suivant :  
  
 [http:\/\/www.openmp.org](http://www.openmp.org)  
  
 Les directives, les fonctions de bibliothèque, et les variables d'environnement définies dans ce document permettent aux utilisateurs de créer et gérer des programmes parallèles tout en permettant la portabilité.  Les directives étendent le modèle de programmation séquentiel C et C\+\+ avec plusieurs éléments de données \(SPMD\) de programme unique, partage d'éléments de travail, et éléments de synchronisation, et il fournit la prise en charge du partage et de la privatisation des données.  Les compilateurs qui prennent en charge l'API d'OpenMP C et C\+\+ incluront une option de ligne de commande du compilateur qui active et permet l'interprétation de les directives de compilateur d'OpenMP.