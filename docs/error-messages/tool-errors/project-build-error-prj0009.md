---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0009 | Microsoft Docs"
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
  - "PRJ0009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0009"
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de g&#233;n&#233;ration de projet PRJ0009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le journal de génération n'a pu être ouvert en écriture.  
  
 **Assurez\-vous que le fichier n'est pas ouvert par un autre processus et qu'il n'est pas protégé en écriture.**  
  
 Après avoir attribué à la propriété **Journal de génération** la valeur **Oui** et exécuté une génération ou une régénération, Visual C\+\+ n'a pas pu ouvrir le journal de la génération en mode exclusif.  
  
 Vérifiez le paramétrage de **Journal de génération** en ouvrant la boîte de dialogue **Options** \(menu **Outils**, commande **Options**\), et en sélectionnant **Génération de VC\+\+** dans le dossier **Projets**.  Le fichier de génération se nomme BuildLog.htm et est écrit dans le répertoire intermédiaire $\(IntDir\).  
  
 Les raisons possibles de cette erreur sont les suivantes :  
  
-   Vous exécutez deux processus de Visual C\+\+ et essayez de générer la même configuration du même projet dans ces deux processus simultanément.  
  
-   Le fichier journal de la génération est ouvert dans un processus qui verrouille le fichier.  
  
-   L'utilisateur n'est pas autorisé à créer un fichier.  
  
-   L'utilisateur actuel n'a pas accès en écriture au fichier BuildLog.htm.