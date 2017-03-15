---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0024 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0024"
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur de g&#233;n&#233;ration de projet PRJ0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le chemin Unicode 'chemin' n'a pas pu être traduit dans la page de codes ANSI de l'utilisateur.  
  
 ***chemin d'accès***  correspond à la version Unicode d'origine de la chaîne du chemin d'accès.  Cette erreur peut survenir quand un chemin Unicode ne peut pas être converti directement en ANSI pour la page de codes système en cours.  
  
 Cette erreur peut se produire si vous travaillez sur un projet qui a été développé sur un système utilisant une page de codes qui ne se trouve pas sur votre ordinateur.  
  
 Pour corriger cette erreur, mettez à jour le chemin d'accès de façon à utiliser le texte ANSI ou installez la page de codes sur votre ordinateur et définissez\-la en tant que valeur système par défaut.