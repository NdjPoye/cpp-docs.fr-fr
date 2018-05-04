---
title: Types de liaison | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
- linkage [C++], types of
- types [C++], linkage
- internal linkage, types of linkage
- external linkage, linkage types
ms.assetid: 41326c7f-4602-4bad-a648-697604858ba0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfddf0105603311179340a0c6b0b2e8fb328b134
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="types-of-linkage"></a>Types de liaison
La façon dont les noms des objets et des fonctions sont partagés entre les unités de traduction est appelée liaison. Ces noms peuvent avoir :  
  
-   Une liaison interne, auquel cas ils font référence uniquement aux éléments de programme à l'intérieur de leurs propres unités de traduction. Ils ne sont pas partagés avec d'autres unités de traduction.  
  
     Le même nom dans une autre unité de traduction peut faire référence à un autre objet ou à une autre classe. Les noms avec une liaison interne sont parfois désignés comme étant locaux par rapport à leurs unités de traduction.  
  
     Voici un exemple de déclaration d'un nom avec une liaison interne :  
  
    ```  
    static int i;   // The static keyword ensures internal linkage.  
    ```  
  
-   Une liaison externe, auquel cas ils peuvent faire référence aux éléments de programme dans toute unité de traduction du programme. L'élément de programme est partagée entre les unités de traduction.  
  
     Il est garanti que le même nom dans une autre unité de traduction fait référence au même objet ou à la même classe. Les noms avec liaison externe sont parfois désignés comme étant globaux.  
  
     Voici un exemple de déclaration d'un nom avec une liaison externe :  
  
    ```  
    extern int i;  
    ```  
  
-   Aucune liaison, auquel cas ils font référence à des entités uniques. Le même nom dans une autre portée peut ne pas faire référence au même objet. Une énumération en est un exemple. (Notez toutefois que vous pouvez passer un pointeur vers un objet sans liaison. Cela rend l'objet accessible dans d'autres unités de traduction.)  
  
## <a name="see-also"></a>Voir aussi  
 [Programme et liaison](../cpp/program-and-linkage-cpp.md)