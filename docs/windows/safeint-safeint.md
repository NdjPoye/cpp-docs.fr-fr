---
title: SafeInt::SafeInt | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9820227384866cdb1a6470ebd9650187848334c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt
Construit un objet `SafeInt`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `i`  
 La valeur de la nouvelle `SafeInt` objet. Ce doit être un paramètre de type T ou U, en fonction du constructeur.  
  
 [in] `b`  
 La valeur booléenne pour le nouveau `SafeInt` objet.  
  
 [in] `u`  
 A `SafeInt` de type U. La nouvelle `SafeInt` objet aura la même valeur que `u`, mais sera de type T.  
  
 U  
 Le type de données stockées dans le `SafeInt`. Cela peut être une valeur booléenne, un caractère ou un entier de type. Si elle est de type entier, il peut être signé ou non signé et être comprise entre 8 et 64 bits.  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations sur les types de modèles `T` et `E`, consultez [SafeInt, classe](../windows/safeint-class.md).  
  
 Le paramètre d’entrée pour le constructeur, `i` ou `u`, doit être un type booléen, caractère ou entier. S’il s’agit d’un autre type de paramètre, le `SafeInt` classe appelle [static_assert](../cpp/static-assert.md) pour indiquer un paramètre d’entrée non valide.  
  
 Les constructeurs qui utilisent le type de modèle `U` automatiquement de convertir le paramètre d’entrée pour le type spécifié par `T`. La `SafeInt` classe convertit les données sans aucune perte de données. Il signale au gestionnaire d’erreurs `E` si elle ne peut pas convertir les données en type `T` sans perte de données.  
  
 Si vous créez un `SafeInt` à partir d’un paramètre booléen, vous devez initialiser la valeur immédiatement. Impossible de construire un `SafeInt` en utilisant le code `SafeInt<bool> sb;`. Cela génère une erreur de compilation.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** safeint.h  
  
 **Namespace :** msl::utilities  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeInt (classe)](../windows/safeint-class.md)   
 [SafeIntException Class](../windows/safeintexception-class.md)