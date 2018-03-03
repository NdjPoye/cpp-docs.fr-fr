---
title: "PRJ0034 d’erreur de Build de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0034
dev_langs:
- C++
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e68097d234519cdea75875d355ef798672ad4b22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0034"></a>Erreur de génération de projet PRJ0034
La propriété 'Dépendances supplémentaires' pour personnalisée au niveau du projet étape de génération contenait 'macro' dont l’évaluation donne 'expansion_macro'.  
  
 Une étape de génération personnalisée sur un projet contenait une erreur dans ses dépendances supplémentaires, probablement en raison d’un problème d’évaluation de macro. Cette erreur peut aussi signifier que le chemin d’accès est incorrect, contenant des caractères ou des combinaisons de caractères qui ne sont pas autorisés dans un chemin d’accès de fichier.  
  
 Pour résoudre cette erreur, corrigez la macro ou corrigez la spécification de chemin d’accès. Le chemin d’accès évalué est un chemin d’accès absolu du répertoire de projet.