---
title: ctype&lt;char&gt;, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
- std::ctype<char>
- std.ctype<char>
dev_langs:
- C++
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
caps.latest.revision: 20
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 0acae30ecbe670c87179f4cc2f5a2b8066ef3a4c
ms.lasthandoff: 02/24/2017

---
# <a name="ctypeltchargt-class"></a>ctype&lt;char&gt;, classe
Classe constituant une spécialisation explicite de la classe de modèle **ctype\<CharType**> en type `char`, décrivant un objet qui peut servir de facette de paramètres régionaux pour caractériser diverses propriétés d’un caractère de type `char`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <>  
class ctype<char>  
: public ctype_base  
{  
public:  
    typedef char _Elem;  
    typedef _Elem char_type;  
    bool is(
    mask _Maskval,  
    _Elem _Ch) const;

 
    const _Elem* is(
    const _Elem* first,  
    const _Elem* last,  
    mask* dest) const;

 
    const _Elem* scan_is(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    const _Elem* scan_not(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    _Elem tolower(
    _Elem _Ch) const;

 
    const _Elem* tolower(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem toupper(
    _Elem _Ch) const;

 
    const _Elem* toupper(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem widen(
    char _Byte) const;

 
    const _Elem* widen(
    const char* first,  
    const char* last,  
    _Elem* dest) const;

 
    const _Elem* _Widen_s(
    const char* first,  
    const char* last,  
    _Elem* dest,  
    size_t dest_size) const;

 
    _Elem narrow(
    _Elem _Ch,  
    char _Dflt = '\0') const;

 
    const _Elem* narrow(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest) const;

 
    const _Elem* _Narrow_s(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest,  
    size_t dest_size) const;

 
    static locale::id& id;  
    explicit ctype(
    const mask* _Table = 0,  
    bool _Deletetable = false,  
    size_t _Refs = 0);

protected:  
    virtual ~ctype();
//other protected members  
};  
```  
  
## <a name="remarks"></a>Notes  
 La spécialisation explicite diffère de la classe de modèle de plusieurs façons :  
  
-   Un objet de classe ctype< `char`> stocke un pointeur vers le premier élément d’un tableau de masque ctype, un tableau de UCHAR_MAX + 1 éléments de type **ctype_base::mask**. Il stocke également un objet booléen qui indique si le tableau doit être supprimé (à l’aide de `operator delete[]`) quand l’objet ctype\< **Elem**> est détruit.  
  
-   Son seul constructeur public vous permet de spécifier **tab**, le tableau de masque ctype, et **del**, l’objet booléen qui a la valeur true si le tableau doit être supprimé quand l’objet ctype< `char`> est détruit, ainsi que les références de paramètre reference-count.  
  
-   La fonction membre protégée **table** retourne le tableau de masque ctype stocké.  
  
-   L’objet de membre statique **table_size** spécifie le nombre minimal d’éléments dans un tableau de masque ctype.  
  
-   La fonction membre statique protégée **classic_table**( retourne le tableau de masque ctype approprié pour les paramètres régionaux « C ».  
  
-   Il n’y a aucune fonction membre virtuelle protégée [do_is](../standard-library/ctype-class.md#ctype__do_is), [do_scan_is](../standard-library/ctype-class.md#ctype__do_scan_is) ou [do_scan_not](../standard-library/ctype-class.md#ctype__do_scan_not). Les fonctions membres publiques correspondantes effectuent les opérations équivalentes.  
  
 Les fonctions membres [do_narrow](../standard-library/ctype-class.md#ctype__do_narrow) et [do_widen](../standard-library/ctype-class.md#ctype__do_widen) copient des éléments non modifiés.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [facet, classe](http://msdn.microsoft.com/Library/dd4f12f5-cb1b-457f-af56-2fb204216ec1)   
 [ctype_base, classe](../standard-library/ctype-base-class.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)


