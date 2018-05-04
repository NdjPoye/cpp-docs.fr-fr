---
title: Instructions composées (blocs) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a8823935ee2f871cdc033aec23f05fc108244e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="compound-statements-blocks"></a>Instructions composées (blocs)
Une instruction composée se compose de zéro ou plusieurs instructions entourées accolades (**{}**). Une instruction composée peut être utilisée partout où une instruction est attendue. Les instructions composées sont généralement appelées « blocs ».  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>Notes  
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