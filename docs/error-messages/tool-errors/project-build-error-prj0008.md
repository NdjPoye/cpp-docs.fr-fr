---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0008"
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur de g&#233;n&#233;ration de projet PRJ0008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Impossible de supprimer le fichier 'fichier'.  
  
 **Assurez\-vous que le fichier n'est pas ouvert par un autre processus et qu'il n'est pas protégé en écriture.**  
  
 Lors d'une opération de régénération ou de nettoyage, Visual C\+\+ supprime tous les fichiers intermédiaires et de sortie connus de la génération, ainsi que tous les fichiers répondant aux spécifications génériques de la propriété **Extensions à supprimer lors du nettoyage** dans la [page de propriétés Général, Paramètres de configuration](../../ide/general-property-page-project.md).  
  
 Cette erreur apparaîtra si Visual C\+\+ n'est pas en mesure de supprimer un fichier.  Pour corriger cette erreur, rendez le fichier et son répertoire accessibles en écriture pour l'utilisateur exécutant la génération.