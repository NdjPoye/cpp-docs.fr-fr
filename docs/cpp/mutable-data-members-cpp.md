---
title: Données membres mutables (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7dd639cbf1ef076dee6e447f317533bf12dae10
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="mutable-data-members-c"></a>Membres de données mutables (C++)
Ce mot clé peut être appliqué uniquement aux données membres non statiques et non constantes d'une classe. Si un membre de données est déclaré `mutable`, il est permis d’affecter une valeur à ce membre de données à partir d’un **const** fonction membre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
mutable member-variable-declaration;  
```  
  
## <a name="remarks"></a>Notes  
 Par exemple, le code suivant est compilé sans erreur car `m_accessCount` a été déclaré comme étant `mutable` et peut donc être modifié par `GetFlag` bien que `GetFlag` soit une fonction membre const.  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)