---
title: "PRJ0041 d’avertissement de génération de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 231b58cb0c13d1a3f87e010a5100da564b0be806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-warning-prj0041"></a>Avertissement de génération de projet PRJ0041
Impossible de trouver manquant dépendance 'dépendance' fichier 'fichier'. Votre projet peut être généré, mais peut sembler obsolète tant que ce fichier se trouve.  
  
 Un fichier (fichier de ressources ou.idl/.odl, par exemple, contenait une instruction include que le système de projet n’a pas pu résoudre.  
  
 Étant donné que le système de projet ne traite pas les instructions de préprocesseur (#if, par exemple), l’instruction en fait peut-être pas partie de la build.  
  
 Pour résoudre cet avertissement, supprimez tout le code dans les fichiers .rc inutile ou ajouter des fichiers d’espace réservé du nom approprié.