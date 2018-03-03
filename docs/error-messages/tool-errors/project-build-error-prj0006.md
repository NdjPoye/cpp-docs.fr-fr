---
title: "PRJ0006 d’erreur de Build de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0006
dev_langs:
- C++
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 817450fb6b72f985d7ff49f7e65f9dfa0933b4d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0006"></a>Erreur de génération de projet PRJ0006
N’a pas pu ouvrir le fichier temporaire 'fichier'. Assurez-vous que le fichier existe et que le répertoire n’est pas protégé en écriture.  
  
 Visual C++ n’a pas pu créer un fichier temporaire pendant le processus de génération. Raisons sont les suivantes :  
  
-   Pas de répertoire temporaire.  
  
-   Répertoire temporaire en lecture seule.  
  
-   Espace disque insuffisant.  
  
-   Le dossier $ (IntDir) est en lecture seule ou contient des fichiers temporaires qui sont en lecture seule.  
  
 Cette erreur se produit également après l’erreur PRJ0007 : Impossible de créer le répertoire de sortie 'répertoire'. L’erreur PRJ0007 signifie que le répertoire $ (IntDir) n’a pas pu être créé, ce qui implique la création de fichiers temporaires échouera également.  
  
 Fichiers temporaires sont créés chaque fois que vous spécifiez :  
  
-   Un fichier réponse.  
  
-   Une étape de génération personnalisée.  
  
-   Un événement de build.