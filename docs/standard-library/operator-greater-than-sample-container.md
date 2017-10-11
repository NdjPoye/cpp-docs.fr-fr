---
title: operator&gt; (&lt;sample container&gt;) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::operator>
- operator>
- std::>
- '>'
dev_langs:
- C++
helpviewer_keywords:
- '> operator, comparing specific objects'
- operator >
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 57550a5bb1daa5621b54d8cc22f8803cf0f936dd
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="operatorgt-ltsample-containergt"></a>operator&gt; (&lt;sample container&gt;)
> [!NOTE]
>  Cette rubrique fait partie de la documentation Visual C++. Elle fournit un exemple non opérationnel de conteneurs utilisés dans la bibliothèque standard C++. Pour plus d’informations, consultez [Conteneurs disponibles dans la bibliothèque standard C++](../standard-library/stl-containers.md).  
  
 Surcharge **operator>** pour comparer deux objets de la classe de modèle [Container](../standard-library/sample-container-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty>  
bool operator*gt;(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne `right < left`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<sample container>](../standard-library/sample-container.md)


