---
title: "la région, endregion | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs:
- C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fda2aba5fdb0aa83066c1762822bfce5fc5f6b4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="region-endregion"></a>region, endregion
**#pragma region** vous permet de spécifier un bloc de code que vous pouvez développer ou réduire lorsque vous utilisez la [fonctionnalité mode plan](/visualstudio/ide/outlining) de l’éditeur de Code Visual Studio.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### <a name="parameters"></a>Paramètres  
 `comment`(facultatif)  
 Commentaire qui s'affiche dans l'éditeur de code.  
  
 *nom*(facultatif)  
 Nom de la région.  Ce nom s'affiche dans l'éditeur de code.  
  
## <a name="remarks"></a>Notes  
 **#pragma endregion** marque la fin d’un **#pragma region** bloc.  
  
 A `#region` bloc doit se terminer par **#pragma endregion**.  
  
## <a name="example"></a>Exemple  
  
```  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)