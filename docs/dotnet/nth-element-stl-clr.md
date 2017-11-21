---
title: nth_element (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::nth_element
dev_langs: C++
helpviewer_keywords: nth_element function [STL/CLR]
ms.assetid: 19fc1695-62a9-4f85-9920-d153c1c6481f
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e0dc54dda65163f5682b2ee20e5e0b08a63acbd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="nthelement-stlclr"></a>nth_element (STL/CLR)
Divise une plage d’éléments, en recherchant le `n`ième élément de la séquence de la plage afin que tous les éléments le précédant lui soient inférieur ou égal à celui-ci et tous les éléments qui suivent dans la séquence sont supérieurs ou égaux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class _RanIt> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last,  
        _Pr _Pred);  
```  
  
## <a name="remarks"></a>Remarques  
 Cette fonction comporte comme la fonction de la bibliothèque Standard C++ `nth_element`. Pour plus d’informations, consultez [nth_element](../standard-library/algorithm-functions.md#nth_element).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/algorithme >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)