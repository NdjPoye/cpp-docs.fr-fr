---
title: 2.6.2 construction critical | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c658b32536404dde1a693582e78bfbedc2823b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="262-critical-construct"></a>2.6.2 Construction critical
Le **critique** directive identifie une construction qui restreint l’exécution du bloc structuré associé à un seul thread à la fois. La syntaxe de la **critique** la directive est la suivante :  
  
```  
#pragma omp critical [(name)]  new-linestructured-block  
```  
  
 Facultatif *nom* peut être utilisé pour identifier la zone critique. Les identificateurs utilisés pour identifier une région critique ont une liaison externe et sont dans un espace de noms qui diffèrent dans les espaces de noms utilisés par les étiquettes, les balises, les membres et les identificateurs ordinaires.  
  
 Un thread attend au début d’une zone critique jusqu'à ce qu’aucun autre thread n’exécute une région critique (n’importe où dans le programme) portant le même nom. Tous les sans nom **critique** directives de mappent le même nom non spécifié.