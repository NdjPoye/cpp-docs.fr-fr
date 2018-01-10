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
caps.latest.revision: "15"
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 9b9f64f67b1649c1c2f3d65f63636fd62601d06a
ms.sourcegitcommit: a7e4956c1150273e8dd39fda8b41655a6cf2cb98
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt;, fonctions

Ce sont les fonctions de modèle global définies dans &lt;ostream&gt;. Pour les fonctions membres, consultez la [basic_ostream, classe](basic-ostream-class.md) documentation.

||||
|-|-|-|
|[endl](#endl)|[ends](#ends)|[flush](#flush)|
|[swap](#swap)|

## <a name="endl"></a>endl

Met fin à une ligne et vide la mémoire tampon.

```cpp
template class<Elem, Tr> 
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Paramètres

*Elem*  
Type de l’élément.

*Ostr*  
Un objet de type **basic_ostream**.

*Tr*  
Caractéristiques du caractère.

### <a name="return-value"></a>Valeur de retour

Un objet de type **basic_ostream**.

### <a name="remarks"></a>Notes

Les appels manipulateur *Ostr*.[ Put](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ élargir](../standard-library/basic-ios-class.md#widen)('\n')), puis appelle *Ostr*.[ vider](../standard-library/basic-ostream-class.md#flush). Elle retourne *Ostr*.

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

## <a name="ends"></a>ends

Met fin à une chaîne.

```cpp
template class<Elem, Tr> 
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Paramètres

*Elem*  
Type de l’élément.

*Ostr*  
Un objet de type **basic_ostream**.

*Tr*  
Caractéristiques du caractère.

### <a name="return-value"></a>Valeur de retour

Un objet de type **basic_ostream**.

### <a name="remarks"></a>Notes

Les appels manipulateur *Ostr*.[ Put](../standard-library/basic-ostream-class.md#put)(*Elem*('\0')). Elle retourne *Ostr*.

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

## <a name="flush"></a>flush

Vide la mémoire tampon.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Paramètres

*Elem*  
Type de l’élément.

*Ostr*  
Un objet de type **basic_ostream**.

*Tr*  
Caractéristiques du caractère.

### <a name="return-value"></a>Valeur de retour

Un objet de type **basic_ostream**.

### <a name="remarks"></a>Notes

Les appels manipulateur *Ostr*.[ vider](../standard-library/basic-ostream-class.md#flush). Elle retourne *Ostr*.

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

## <a name="swap"></a>swap

Échange les valeurs de deux **basic_ostream** objets.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Paramètres

*Elem*  
Type de l’élément.

*Tr*  
Caractéristiques du caractère.

*left*  
Référence lvalue à un **basic_ostream** objet.

*right*  
Référence lvalue à un **basic_ostream** objet.

### <a name="remarks"></a>Notes

La fonction de modèle **swap** exécute `left.swap(right)`.

## <a name="see-also"></a>Voir aussi

[\<ostream>](../standard-library/ostream.md)  
