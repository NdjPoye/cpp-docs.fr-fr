---
title: 2.4 constructions de partage de travail | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5353bc51f6a701201520f700057ef76ce7778191
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="24-work-sharing-constructs"></a>2.4 Constructions de partage de travail
Une construction de partage de travail répartit l’exécution de l’instruction associée parmi les membres de l’équipe que vous rencontrez. Les directives de partage de travail ne pas lancent de nouveaux threads, et il n’existe aucune barrière implicite sur ENTRÉE pour une construction de partage de travail.  
  
 La séquence de partage de travail construit et **barrière** directives rencontrés doivent être identiques pour chaque thread dans une équipe.  
  
 OpenMP définit les constructions de partage de travail suivantes, et que ceux-ci sont décrits dans les sections qui suivent :  
  
-   **pour** (directive)  
  
-   **sections** (directive)  
  
-   **seul** (directive)