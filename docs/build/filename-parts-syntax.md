---
title: Syntaxe de parties de nom de fichier | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a481f8c461cb4fddd4acb090edb2f2b5fd18636d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="filename-parts-syntax"></a>Syntaxe des éléments d'un nom de fichier
Syntaxe de parties de nom de fichier dans les commandes représente les composants du nom de fichier dépendant premier (qui peut être un dépendant implicite). Composants de nom de fichier sont lecteur du fichier, chemin d’accès, nom de base et extension spécifiée, pas comme il existe sur le disque. Utilisez **%s** pour représenter le nom de fichier complet. Utilisez **% &#124;** [*parties*]**F** (une barre verticale caractère suit le signe de pourcentage) pour représenter les parties du nom de fichier, où *parties* peut être zéro ou plusieurs des lettres suivantes, dans n’importe quel ordre.  
  
|Lettre|Description|  
|------------|-----------------|  
|Aucune lettre|Nom complet (identique à **%s**)|  
|**d**|Lecteur|  
|**p**|Chemin d’accès|  
|**f**|Nom de base de fichier|  
|**e**|Extension de fichier|  
  
 Par exemple, si le nom de fichier est c:\prog.exe :  
  
-   %s sera c:\prog.exe  
  
-   % &#124; F sera c:\prog.exe  
  
-   % &#124; se dF c  
  
-   % &#124; pF sera le c:\  
  
-   % &#124; fF sera le prog  
  
-   % &#124; eF sera l’exe  
  
## <a name="see-also"></a>Voir aussi  
 [Commandes dans un makefile](../build/commands-in-a-makefile.md)