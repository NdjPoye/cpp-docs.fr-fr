---
title: __if_not_exists, instruction | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __if_not_exists
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 9
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
ms.openlocfilehash: 5eff74bd6405d7ec63b3cc8fbea968df984fddb8
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="ifnotexists-statement"></a>__if_not_exists, instruction
L'instruction `__if_not_exists` vérifie si l'identificateur spécifié existe. S'il n'existe pas, le bloc d'instructions spécifié est exécuté.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`identifier`|Identificateur dont vous voulez tester l'existence.|  
|`statements`|Une ou plusieurs instructions à exécuter si `identifier` n’existe pas.|  
  
## <a name="remarks"></a>Remarques  
  
> [!CAUTION]
>  Pour obtenir les résultats les plus fiables, utilisez l'instruction `__if_not_exists` sous les contraintes suivantes.  
  
-   Appliquez l'instruction `__if_not_exists` uniquement aux types simples, et non aux modèles.  
  
-   Appliquez l'instruction `__if_not_exists` aux identificateurs à l'intérieur ou à l'extérieur d'une classe. N'appliquez pas l'instruction `__if_not_exists` aux variables locales.  
  
-   Utilisez l'instruction `__if_not_exists` uniquement dans le corps d'une fonction. En dehors du corps d'une fonction, l'instruction `__if_not_exists` peut tester uniquement les types entièrement définis.  
  
-   Lorsque vous vérifiez la présence de fonctions surchargées, vous ne pouvez pas effectuer le test sur une forme spécifique de la surcharge.  
  
 Le complément à la `__if_not_exists` instruction est la [__if_exists](../cpp/if-exists-statement.md) instruction.  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple sur l’utilisation `__if_not_exists`, consultez [__if_exists, instruction](../cpp/if-exists-statement.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions de sélection](../cpp/selection-statements-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 [__if_exists, instruction](../cpp/if-exists-statement.md)
