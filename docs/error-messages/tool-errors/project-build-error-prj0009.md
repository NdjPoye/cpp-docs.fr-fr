---
title: "PRJ0009 d’erreur de Build de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0009
dev_langs: C++
helpviewer_keywords: PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ee183c24cf330b54a335efbd0bbe2b00e18d209
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0009"></a>Erreur de génération de projet PRJ0009
Build journal n’a pas pu être ouvert en écriture.  
  
 **Assurez-vous que le fichier n’est pas ouvert par un autre processus et qu’il n’est pas protégé en écriture.**  
  
 Après avoir défini la **journal de génération** propriété **Oui** et effectuez une génération ou une régénération, Visual C++ n’a pas pu ouvrir le journal de génération en mode exclusif.  
  
 Inspecter le **journal de génération** définition en ouvrant le **Options** boîte de dialogue (sur le **outils** menu, cliquez sur **Options** commande), puis en sélectionnant **VC ++ Build** dans les **projets** dossier. Le fichier de génération se nomme BuildLog.htm et est écrit dans le répertoire intermédiaire $(IntDir).  
  
 Raisons possibles de cette erreur :  
  
-   Vous exécutez deux processus de Visual C++ et essayez de générer la même configuration du même projet dans les deux simultanément.  
  
-   Le fichier journal de génération est ouvert dans un processus qui verrouille le fichier.  
  
-   L’utilisateur ne dispose pas d’autorisation pour créer un fichier.  
  
-   L’utilisateur actuel ne dispose pas d’un accès en écriture au fichier BuildLog.htm.