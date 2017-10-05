---
title: '&lt;ostream&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 15
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 252a178f1ce71c30bdd830811cbce59b22acc791
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt;, fonctions
||||  
|-|-|-|  
|[swap](#swap)|[endl](#endl)|[ends](#ends)|  
|[flush](#flush)|  
  
##  <a name="endl"></a>  endl  
 Met fin à une ligne et vide la mémoire tampon.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& endl(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Paramètres  
 `Elem`  
 Type de l’élément.  
  
 `Ostr`  
 Objet de type `basic_ostream`.  
  
 `Tr`  
 Caractéristiques de caractère.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet de type `basic_ostream`.  
  
### <a name="remarks"></a>Notes  
 Le manipulateur appelle `Ostr`**.**[put](../standard-library/basic-ostream-class.md#put)( `Ostr`**.** [widen](../standard-library/basic-ios-class.md#widen)( **'\n'**)), puis il appelle `Ostr`**.**[flush](../standard-library/basic-ostream-class.md#flush). Il retourne `Ostr`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostream_endl.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << endl;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="ends"></a>  ends  
 Met fin à une chaîne.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& ends(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Paramètres  
 `Elem`  
 Type de l’élément.  
  
 `Ostr`  
 Objet de type `basic_ostream`.  
  
 `Tr`  
 Caractéristiques de caractère.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet de type `basic_ostream`.  
  
### <a name="remarks"></a>Notes  
 Le manipulateur appelle `Ostr`**.**[put](../standard-library/basic-ostream-class.md#put)( `Elem`( **'\0'**)). Il retourne `Ostr.`  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostream_ends.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "a";  
   cout << "b" << ends;  
   cout << "c" << endl;  
}  
```  
  
```Output  
ab c  
```  
  
##  <a name="flush"></a>  flush  
 Vide la mémoire tampon.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& flush(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Paramètres  
 `Elem`  
 Type de l’élément.  
  
 `Ostr`  
 Objet de type `basic_ostream`.  
  
 `Tr`  
 Caractéristiques de caractère.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet de type `basic_ostream`.  
  
### <a name="remarks"></a>Notes  
 Le manipulateur appelle `Ostr`**.**[flush](../standard-library/basic-ostream-class.md#flush). Il retourne `Ostr`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostream_flush.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << flush;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="swap"></a>  swap  
 Échange les valeurs de deux objets `basic_ostream`.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_ostream<Elem, Tr>& left,  
    basic_ostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Référence lvalue à un objet `basic_ostream`.  
  
 `right`  
 Référence lvalue à un objet `basic_ostream`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle `swap` exécute `left.swap(right)`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<ostream>](../standard-library/ostream.md)


