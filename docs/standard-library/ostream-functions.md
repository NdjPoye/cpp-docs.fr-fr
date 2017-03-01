---
title: '&lt;ostream&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 15
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 44708461657101b1ddad7db76f1c3c8d4df07f3a
ms.lasthandoff: 02/24/2017

---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt;, fonctions
||||  
|-|-|-|  
|[swap](#swap)|[endl](#endl)|[ends](#ends)|  
|[flush](#flush)|  
  
##  <a name="a-nameendla--endl"></a><a name="endl"></a>  endl  
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
 Le manipulateur appelle `Ostr`**.**[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `Ostr`**.** [widen](../standard-library/basic-ios-class.md#basic_ios__widen)( **'\n'**)), puis il appelle `Ostr`**.**[flush](../standard-library/basic-ostream-class.md#basic_ostream__flush). Il retourne `Ostr`.  
  
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
  
##  <a name="a-nameendsa--ends"></a><a name="ends"></a>  ends  
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
 Le manipulateur appelle `Ostr`**.**[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `Elem`( **'\0'**)). Il retourne `Ostr.`  
  
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
  
##  <a name="a-nameflusha--flush"></a><a name="flush"></a>  flush  
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
 Le manipulateur appelle `Ostr`**.**[flush](../standard-library/basic-ostream-class.md#basic_ostream__flush). Il retourne `Ostr`.  
  
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
  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
 Échange les valeurs de deux objets `basic_ostream`.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_ostream<Elem, Tr>& left,  
    basic_ostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Référence lvalue à un objet `basic_ostream`.  
  
 ` right`  
 Référence lvalue à un objet `basic_ostream`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle `swap` exécute ` left.swap(`` right``)`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<ostream>](../standard-library/ostream.md)


