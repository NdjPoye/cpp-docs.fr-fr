---
title: "CType &lt; char &gt; (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ctype<char>"
  - "locale/std::ctype<char>"
  - "std::ctype<char>"
  - "std.ctype<char>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CType < char > (classe)"
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CType &lt; char &gt; (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe est une spécialisation explicite de la classe de modèle **ctype \< CharType**> vers le type `char`, qui décrit un objet pouvant servir de facette de paramètres régionaux pour caractériser diverses propriétés d’un caractère de type `char`.  
  
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
  
## <a name="remarks"></a>Remarques  
 La spécialisation explicite diffère de la classe de modèle de plusieurs façons :  
  
-   Un objet de classe ctype < `char`> stocke un pointeur vers le premier élément d’un tableau de masque ctype, un tableau de UCHAR_MAX + 1 éléments de type **ctype_base::mask**. Il stocke également un objet de type Boolean qui indique si le tableau doit être supprimé (à l’aide de `operator delete[]`) lorsque la fonction ctype \< **Elem**> détruit.  
  
-   Son seul constructeur public vous permet de spécifier **onglet**, la table de masque ctype, et **del**, l’objet Boolean qui est true si le tableau doit être supprimé lorsque la fonction ctype < `char`> objet est détruit, ainsi que les références de paramètre un décompte de références.  
  
-   La fonction membre **table** retourne la table de masque ctype stockée.  
  
-   L’objet de membre statique **table_size** Spécifie le nombre minimal d’éléments dans un tableau de masque ctype.  
  
-   La fonction membre statique **classic_table**(retourne la table de masque ctype appropriée aux paramètres régionaux « C ».  
  
-   Aucune fonction membre virtuelle protégée [do_is](../standard-library/ctype-class.md#ctype__do_is), [do_scan_is](../standard-library/ctype-class.md#ctype__do_scan_is), ou [do_scan_not](../standard-library/ctype-class.md#ctype__do_scan_not). Les fonctions membres publiques correspondantes effectuent les opérations équivalentes eux-mêmes.  
  
 Les fonctions membres [do_narrow](../standard-library/ctype-class.md#ctype__do_narrow) et [do_widen](../standard-library/ctype-class.md#ctype__do_widen) copier des éléments non modifiés.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< paramètres régionaux>  
  
 **Namespace :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Facet, classe](../Topic/facet%20Class.md)   
 [ctype_base, classe](../standard-library/ctype-base-class.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

