---
title: "PRJ0032 d’erreur de Build de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0032
dev_langs: C++
helpviewer_keywords: PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92497027db3a2449914696f03fc86a144a48b62e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0032"></a>Erreur de génération de projet PRJ0032
La propriété 'Sorties' de l’étape de génération personnalisée au niveau du projet contenait 'macro', dont l’évaluation donne 'expansion_macro'.  
  
 Une étape de génération personnalisée sur un projet avait un résultat erroné probablement en raison d’un problème d’évaluation de macro. Cette erreur peut aussi signifier que le chemin d’accès est incorrect, contenant des caractères ou des combinaisons de caractères qui ne sont pas autorisés dans un chemin d’accès de fichier.  
  
 Pour résoudre cette erreur, corrigez la macro ou corrigez la spécification de chemin d’accès. Le chemin d’accès évalué est un chemin d’accès absolu du répertoire de projet.