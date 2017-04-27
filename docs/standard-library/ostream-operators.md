---
title: "&lt;ostream&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 72389624e776a2e8334490c37a5ca628e033ffaa
ms.lasthandoff: 02/24/2017

---
# <a name="ltostreamgt-operators"></a>&lt;ostream&gt;, opérateurs
||  
|-|  
|[operator&lt;&lt;](#operator_lt__lt_)|  
  
##  <a name="operator_lt__lt_"></a>  operator&lt;&lt;  
 Écrit différents types dans le flux.  
  
```
template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const Elem* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    Elem _Ch);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const char* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);

template <class _Elem, class _Tr, class T>
basic_ostream <_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>&& _Ostr,
    Ty val);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Ch`  
 Un caractère.  
  
 `_Elem`  
 Type de l’élément.  
  
 `_Ostr`  
 Objet `basic_ostream`.  
  
 `str`  
 Chaîne caractère.  
  
 `_Tr`  
 Caractéristiques du caractère.  
  
 `val`  
 Type  
  
### <a name="return-value"></a>Valeur de retour  
 flux.  
  
### <a name="remarks"></a>Notes  
 La classe `basic_ostream` définit également plusieurs opérateurs d’insertion. Pour plus d’informations, consultez [basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt_).  
  
 La fonction de modèle  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```  
  
 détermine la longueur N = `traits_type::`[length](../standard-library/char-traits-struct.md#char_traits__length)( `str`) de la séquence à partir de `str`, et insère la séquence. Si N < `_Ostr.`[width](../standard-library/ios-base-class.md#ios_base__width), la fonction insère également une répétition de caractères de remplissage -N `_Ostr.``width`. La répétition précède la séquence si ( `_Ostr`. [flags](../standard-library/ios-base-class.md#ios_base__flags) & `adjustfield` != [left](../standard-library/ios-functions.md#left). Sinon, la répétition suit la séquence. La fonction retourne `_Ostr`.  
  
 La fonction de modèle  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```  
  
 insère l’élément `_Ch`. Si 1 < `_Ostr.width`, la fonction insère également une répétition de caractères de remplissage - 1 `_Ostr.width`. La répétition précède la séquence si `_Ostr.flags & adjustfield != left`. Sinon, la répétition suit la séquence. Elle retourne `_Ostr`.  
  
 La fonction de modèle  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const char *str);
```  
  
 se comporte comme  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```  
  
 sauf que chaque élément `_Ch` de la séquence à partir de `str` est converti en objet de type `Elem` en appelant `_Ostr.`[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `_Ostr.`[widen](../standard-library/basic-ios-class.md#basic_ios__widen)( `_Ch`)).  
  
 La fonction de modèle  
  
``cpp template <class _Elem, class _Tr> basic_ostream<Elem, _Tr>& operator<<( basic_ostream<Elem, _Tr>& _Ostr, char _Ch);
```  
  
 behaves the same as  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```  
  
 sauf que `_Ch` est converti en objet de type `Elem` en appelant `_Ostr.put`( `_Ostr.widen`( `_Ch`)).  
  
 La fonction de modèle  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char *str);
```  
  
 se comporte comme  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```  
  
 (Elle n’a pas besoin d’élargir les éléments avant de les insérer.)  
  
 La fonction de modèle  
  
```cpp  
template <class _Tr>
basic_ostream<char, Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    char _Ch);
```  
  
 se comporte comme  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```  
  
 (Elle n’a pas besoin d’élargir `_Ch` avant de l’insérer.)  
  
 La fonction de modèle  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```  
  
 retourne `_Ostr` << ( `const char *`) `str`.  
  
 La fonction de modèle  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```  
  
 retourne `_Ostr` << ( `char`) `_Ch`.  
  
 La fonction de modèle  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```  
  
 retourne `_Ostr` << ( `const char *`) `str`.  
  
 La fonction de modèle  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```  
  
 retourne `_Ostr` << ( `char`) `_Ch`.  
  
 La fonction de modèle  
  
```cpp  
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```  
  
 retourne `_Ostr` `<<` `val` (et convertit une [référence RValue](../cpp/rvalue-reference-declarator-amp-amp.md) à `_Ostr` en lvalue dans le processus).  
  
### <a name="example"></a>Exemple  
  Consultez [flush](../standard-library/ostream-functions.md#flush) pour obtenir un exemple qui utilise `operator<<`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<ostream>](../standard-library/ostream.md)




