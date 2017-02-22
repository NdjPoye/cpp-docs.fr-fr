---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0006"
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur de g&#233;n&#233;ration de projet PRJ0006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Impossible d'ouvrir le fichier temporaire 'fichier'.Vérifiez que le fichier existe et que le répertoire n'est pas protégé en écriture.  
  
 Visual C\+\+ n'a pas pu créer un fichier temporaire pendant le processus de génération.  Les raisons de l'échec sont les suivantes :  
  
-   Pas de répertoire temporaire.  
  
-   Répertoire temporaire en lecture seule.  
  
-   Espace disque insuffisant.  
  
-   Le dossier $\(IntDir\) est en lecture seule ou contient des fichiers temporaires en lecture seule.  
  
 Cette erreur se produira également à la suite de l'erreur PRJ0007 : Impossible de créer le répertoire de sortie 'répertoire'.  L'erreur PRJ0007 signifie que le répertoire $\(IntDir\) n'a pas pu être créé, ce qui implique que la création de fichiers temporaires échouera également.  
  
 Des fichiers temporaires sont créés chaque fois que vous spécifiez :  
  
-   Un fichier réponse.  
  
-   Une étape de build personnalisée.  
  
-   Un événement de build.