---
title: "Mots réservés | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
dev_langs:
- C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35f9a3e907b72b4b8cf8e673e771832ba3fc0527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="reserved-words"></a>Mots réservés
Les mots suivants sont réservés par l’éditeur de liens. Ces noms peuvent être utilisés en tant qu’arguments dans [les instructions de définition de module](../../build/reference/module-definition-dot-def-files.md) uniquement si le nom est placé entre guillemets doubles ( » »).  
  
||||  
|-|-|-|  
|**APPLOADER**1|**INITINSTANCE**2|**PRÉCHARGEMENT**|  
|**BASE**|**IOPL**|**PRIVÉ**|  
|**CODE**|**BIBLIOTHÈQUE**1|**PROTMODE**2|  
|**CONFORME**|**LOADONCALL**1|**PURE**1|  
|**DONNÉES**|**LONGNAMES**2|**EN LECTURE SEULE**|  
|**DESCRIPTION**|**MOBILE**1|**LECTURE/ÉCRITURE**|  
|**DEV386**|**MOBILE**1|**EN MODE RÉEL ;**1|  
|**POUVANT ÊTRE ÉLIMINÉE**|**PLUSIEURS**|**RÉSIDENT**|  
|**DYNAMIQUE**|**NOM**|**RESIDENTNAME**1|  
|**EXÉCUTER UNIQUEMENT**|**NEWFILES**2|**SECTIONS**|  
|**EXECUTEONLY**|**NODATA**1|**SEGMENTS**|  
|**EXÉCUTIONLECTURE**|**NOIOPL**1|**PARTAGÉ**|  
|**EXETYPE**|**NONAME**|**UNIQUE**|  
|**EXPORTS**|**NON CONFORMES**1|**STACKSIZE**|  
|**FIXE**1|**NONDISCARDABLE**|**STUB**|  
|**FONCTIONS**2|**AUCUN**|**VERSION**|  
|**HEAPSIZE**|**NON PARTAGÉ**|**WINDOWAPI**|  
|**IMPORTATIONS**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**IMPURES**1|**OBJETS**|**WINDOWS**|  
|**INCLURE**2|**ANCIEN**1||  
  
 1 l’éditeur de liens émet un avertissement (« ignoré ») lorsqu’il rencontre ce terme. Toutefois, le mot est toujours réservé.  
  
 2 l’éditeur de liens ignore ce mot, mais n’émet aucun avertissement.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)