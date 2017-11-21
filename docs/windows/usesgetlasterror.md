---
title: usesgetlasterror | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.usesgetlasterror
dev_langs: C++
helpviewer_keywords: usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cf3cfd6d1b0e484b31769184b2fae5a6b012a58e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="usesgetlasterror"></a>usesgetlasterror
Indique à l’appelant que s’il existe une erreur lors de l’appel de cette fonction, puis l’appelant peut ensuite appeler `GetLastError` pour récupérer le code d’erreur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[usesgetlasterror]  
  
```  
  
## <a name="remarks"></a>Remarques  
 Le **usesgetlasterror** attribut C++ a les mêmes fonctionnalités que le [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Consultez le [idl_module](../windows/idl-module.md) exemple pour obtenir un exemple montrant comment utiliser **usesgetlasterror**.  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**module** attribut|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
