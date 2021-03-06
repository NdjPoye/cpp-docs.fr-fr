---
title: Caractères spéciaux dans les Macros | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c271d2f39a4d81776c06a107616170192e82d40d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="special-characters-in-macros"></a>Caractères spéciaux dans les macros
Le signe dièse (#) après qu’une définition indique un commentaire. Pour spécifier un signe dièse littéral dans une macro, utilisez un signe insertion (^), comme dans ^ #.  
  
 Un signe dollar ($) spécifie un appel de macro. Pour spécifier un $ littéral, utilisez $$.  
  
 Pour étendre une définition sur une nouvelle ligne, terminez la ligne par une barre oblique inverse (\\). Lorsque la macro est appelée, le caractère barre oblique inverse et le saut de ligne est remplacé par un espace. Pour spécifier une barre oblique inverse littérale à la fin de la ligne, faites-le précéder d’un signe insertion (^), ou faites-le suivre d’un spécificateur de commentaire (#).  
  
 Pour spécifier un caractère de saut de ligne littéral, terminez la ligne par un signe insertion (^), comme dans :  
  
```  
CMDS = cls^  
dir  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Définition d’une macro NMAKE](../build/defining-an-nmake-macro.md)