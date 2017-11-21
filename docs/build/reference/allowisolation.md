---
title: -ALLOWISOLATION | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /ALLOWISOLATION
dev_langs: C++
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bb0a3973b140e452d3cb1198c5a98ca2caf61a1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="allowisolation"></a>/ALLOWISOLATION
Spécifie un comportement pour la recherche de manifeste.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>Remarques  
 **/ALLOWISOLATION** provoque le système d’exploitation et charger des manifestes.  
  
 **/ALLOWISOLATION** est la valeur par défaut.  
  
 **/ALLOWISOLATION:no** indique que les exécutables sont chargés comme s’il n’existait aucun manifeste et les causes [référence EDITBIN](../../build/reference/editbin-reference.md) pour définir le `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bit dans l’en-tête optional `DllCharacteristics` champ.  
  
 Quand l'isolation est désactivée pour un fichier exécutable, le chargeur Windows ne tente pas de trouver un manifeste d'application pour le processus nouvellement créé. Le nouveau processus n’a un contexte d’activation par défaut, même s’il existe un manifeste dans le fichier exécutable lui-même ou s’il existe un manifeste qui porte le nom *-nom du fichier exécutable*. exe.manifest.  
  
## <a name="see-also"></a>Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)   
 [/ALLOWISOLATION (recherche de manifeste)](../../build/reference/allowisolation-manifest-lookup.md)   
 [Référence des fichiers manifeste](http://msdn.microsoft.com/library/aa375632.aspx)