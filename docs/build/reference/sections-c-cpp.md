---
title: SECTIONS (C/C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SECTIONS
dev_langs: C++
helpviewer_keywords: SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ab2f021a53e8ae685891863500feb3873e13e2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="sections-cc"></a>SECTIONS (C/C++)
Introduit une section d’un ou plusieurs `definitions` qui sont des spécificateurs d’accès dans des sections dans le fichier de sortie de votre projet.  
  
```  
SECTIONS  
definitions  
```  
  
## <a name="remarks"></a>Notes  
 Chaque définition doit être sur une ligne distincte. Le `SECTIONS` mot clé peut être sur la même ligne que la première définition ou sur une ligne précédente. Le fichier .def peut contenir un ou plusieurs `SECTIONS` instructions.  
  
 Cela `SECTIONS` instruction définit les attributs d’une ou plusieurs sections dans le fichier image et peut être utilisée pour substituer les attributs par défaut pour chaque type de section.  
  
 Le format de `definitions` est :  
  
 `.section_name specifier`  
  
 où `.section_name` est le nom d’une section dans l’image de votre programme et `specifier` est un ou plusieurs des modificateurs d’accès suivants :  
  
|Modificateur|Description|  
|--------------|-----------------|  
|`EXECUTE`|La section est exécutable.|  
|`READ`|Permet les opérations de lecture sur les données|  
|`SHARED`|Partage la section parmi tous les processus qui chargent l’image|  
|`WRITE`|Permet les opérations d’écriture sur les données|  
  
 Séparez les noms des spécificateurs par un espace. Exemple :  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS`marque le début d’une liste de section `definitions`. Chaque `definition` doit se trouver sur une ligne distincte. Le `SECTIONS` (mot clé) peut se trouver sur la même ligne que le premier `definition` ou sur une ligne précédente. Le fichier .def peut contenir un ou plusieurs `SECTIONS` instructions. Le `SEGMENTS` (mot clé) est pris en charge comme synonyme de `SECTIONS`.  
  
 Prise en charge des versions antérieures de Visual C++ :  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 Le `CLASS` (mot clé) est pris en charge pour la compatibilité, mais il est ignoré.  
  
 Une façon équivalente pour spécifier des attributs de section consiste à utiliser le [/SECTION](../../build/reference/section-specify-section-attributes.md) option.  
  
## <a name="see-also"></a>Voir aussi  
 [Règles s’appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)