---
title: 2.4 constructions de partage de travail | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 476e4e23b22527accaa095d80b827c95aed58c15
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="24-work-sharing-constructs"></a>2.4 Constructions de partage de travail
Une construction de partage de travail répartit l’exécution de l’instruction associée parmi les membres de l’équipe que vous rencontrez. Les directives de partage de travail ne pas lancent de nouveaux threads, et il n’existe aucune barrière implicite sur ENTRÉE pour une construction de partage de travail.  
  
 La séquence de partage de travail construit et **barrière** directives rencontrés doivent être identiques pour chaque thread dans une équipe.  
  
 OpenMP définit les constructions de partage de travail suivantes, et que ceux-ci sont décrits dans les sections qui suivent :  
  
-   **pour** (directive)  
  
-   **sections** (directive)  
  
-   **seul** (directive)