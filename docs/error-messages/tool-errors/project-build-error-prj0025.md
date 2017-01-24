---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0025 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0025"
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de g&#233;n&#233;ration de projet PRJ0025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le fichier batch 'fichier' contient du code Unicode qui n'a pas pu être traduit dans la page de codes ANSI de l'utilisateur.  
  
 ***Contenu UNICODE du fichier***  
  
 Le système de projet a trouvé un contenu Unicode, dans une règle de génération personnalisée ou un événement de build, qui ne peut être traduit correctement dans la page de codes ANSI en cours de l'utilisateur.  
  
 Pour corriger cette erreur, mettez à jour le contenu de la règle de génération ou de l'événement de build de façon à utiliser ANSI ou installez la page de codes sur votre ordinateur et définissez\-la en tant que valeur système par défaut.  
  
 Pour plus d'informations sur les étapes de build personnalisée et les événements de build, consultez [Présentation des étapes de build personnalisée et des événements de build](../../ide/understanding-custom-build-steps-and-build-events.md).