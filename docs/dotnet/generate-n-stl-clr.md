---
title: generate_n (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::generate_n
dev_langs: C++
helpviewer_keywords: generate_n function [STL/CLR]
ms.assetid: 2f56e649-7a6f-4861-ae49-d0b25f5cd50c
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 15a6d68913bd64d8f5022efa4344c1e3749451f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="generaten-stlclr"></a>generate_n (STL/CLR)
Assigne les valeurs générées par un objet de fonction à un nombre spécifié d'éléments d'une plage, et retourne à la position située juste après la dernière valeur assignée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class _OutIt, class _Diff, class _Fn0> inline  
    void generate_n(_OutIt _Dest, _Diff _Count, _Fn0 _Func);  
```  
  
## <a name="remarks"></a>Remarques  
 Cette fonction comporte comme la fonction de la bibliothèque Standard C++ `generate_n`. Pour plus d’informations, consultez [generate_n](../standard-library/algorithm-functions.md#generate_n).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/algorithme >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)