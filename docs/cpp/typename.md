---
title: TypeName | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- typename_cpp
dev_langs:
- C++
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
caps.latest.revision: 7
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
ms.openlocfilehash: 95283efc5d3b92a461ba6507e669f6f3e2af2689
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="typename"></a>typename
Dans les définitions de modèle, fournit une indication au compilateur qu’un identificateur inconnu est un type. Dans les listes de paramètres de modèle, est utilisé pour spécifier un paramètre de type.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
typename identifier;  
```  
  
## <a name="remarks"></a>Remarques  
 Ce mot clé doit être utilisé si un nom dans une définition de modèle est un nom qualifié qui dépend d’un argument de modèle ; Il est facultatif si le nom qualifié n’est pas dépendant. Pour plus d’informations, consultez [modèles et résolution de noms](../cpp/templates-and-name-resolution.md).  
  
 **nom de type** peut être utilisé par n’importe quel type de n’importe où dans une définition ou déclaration de modèle. Il n’est pas autorisé dans la liste des classes de base sauf sous forme d’argument template pour une classe de base de modèle.  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 Le **typename** mot clé peut également être utilisé à la place de **classe** dans le paramètre de modèle. Par exemple, les instructions suivantes sont sémantiquement équivalentes :  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>Exemple  
  
```  
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles](../cpp/templates-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)
