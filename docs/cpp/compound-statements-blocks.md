---
title: "Instructions composées (blocs) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs:
- C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9dc28fde0ab2cf5b21771347554d0c664b7f462d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="compound-statements-blocks"></a>Instructions composées (blocs)
Une instruction composée se compose de zéro ou plusieurs instructions entourées accolades (**{}**). Une instruction composée peut être utilisée partout où une instruction est attendue. Les instructions composées sont généralement appelées « blocs ».  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>Remarques  
 L’exemple suivant utilise une instruction composée comme le *instruction* dans le cadre de la **si** instruction (consultez [if instruction](../cpp/if-else-statement-cpp.md) pour plus d’informations sur la syntaxe) :  
  
```  
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
{
    Balance -= Amount;  
}
```  
  
> [!NOTE]
>  Comme une déclaration est une instruction, une déclaration peut être une des instructions dans le *-liste d’instructions*. Par conséquent, les noms déclarés au sein d'une instruction composée, mais pas explicitement déclarés comme statiques, ont une portée locale et (pour les objets) une durée de vie locale. Consultez [étendue](../cpp/scope-visual-cpp.md) pour plus d’informations sur le traitement des noms avec une portée locale.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble des instructions C++](../cpp/overview-of-cpp-statements.md)
