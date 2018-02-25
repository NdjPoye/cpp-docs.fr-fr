---
title: operator&gt;= | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- operator>=
- std::>=
- std.operator>=
- '>='
- std.>=
- std::operator>=
dev_langs:
- C++
helpviewer_keywords:
- '>= operator, comparing specific objects'
- operator >=
- operator>=
ms.assetid: 14fbebf5-8b75-4afa-a51b-3112d31c07cf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5473215276d9de13515f83e3d29727953e9a0a49
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="operatorgt"></a>operator&gt;=
> [!NOTE]
>  Cette rubrique fait partie de la documentation Visual C++. Elle fournit un exemple non opérationnel de conteneurs utilisés dans la bibliothèque standard C++. Pour plus d’informations, consultez [Conteneurs de la bibliothèque standard C++](../standard-library/stl-containers.md).  
  
 Surcharge **operator>=** pour comparer deux objets de la classe de modèle [Container](../standard-library/sample-container-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty>  
bool operator>=(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne `!(left < right)`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<sample container>](../standard-library/sample-container.md)

