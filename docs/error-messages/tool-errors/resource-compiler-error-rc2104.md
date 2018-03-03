---
title: Erreur RC2104 du compilateur de ressources | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2104
dev_langs:
- C++
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce7fa189e03ec907c4b42f381096f095d5df734a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2104"></a>Erreur RC2104 du compilateur de ressources 
mot clé ou nom de clé non défini : clé  
  
 Le mot clé ou le nom de clé spécifié n'est pas défini.  
  
 Cette erreur est souvent due à une erreur typographique dans la définition de la ressource ou dans le fichier d'en-tête inclus. Elle peut aussi être liée à un fichier d'en-tête manquant.  
  
 Pour résoudre ce problème, recherchez le fichier d'en-tête qui doit contenir le mot clé ou le nom de clé défini et vérifiez qu'il est inclus dans votre fichier de ressources. Assurez-vous aussi que le mot clé ou le nom de clé est correctement orthographié. Si votre projet a été créé avec un en-tête précompilé et que vous le supprimez par la suite, assurez-vous que le fichier de ressources contient toujours les en-têtes nécessaires.  
  
 Pour vérifier les mots clés définis et les noms de clé dans votre fichier de ressources dans Visual Studio, ouvrez le **affichage des ressources** fenêtre, dans la barre de menus, choisissez **vue**, **affichage des ressources**, et Ouvrez le menu contextuel pour le fichier .rc, puis choisissez **symboles des ressources** pour afficher la liste des symboles définis. Pour modifier les en-têtes inclus, ouvrez le menu contextuel pour le fichier .rc et choisissez **Include des ressources**.  
  
 Si vous obtenez le message suivant :  
  
```  
undefined keyword or key name: MFT_STRING   
```  
  
 ouvrez \MCL\MFC\Include\AfxRes.h et ajoutez cette directive include :  
  
```  
#include <winresrc.h>  
```