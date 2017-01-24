---
title: "collate_byname, classe | Microsoft Docs"
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
  - "std::collate_byname"
  - "locale/std::collate_byname"
  - "std.collate_byname"
  - "collate_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collate_byname (classe)"
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# collate_byname, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de modèle dérivée qui décrit un objet susceptible de servir de facette d'assemblage de paramètres régionaux donnés, permettant ainsi la récupération d'informations spécifiques à une zone culturelle concernant les conventions de tri de chaîne.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Locname`  
 Paramètres régionaux nommée.  
  
 `_Refs`  
 Un décompte de références initial.  
  
## <a name="remarks"></a>Remarques  
 La classe de modèle décrit un objet pouvant servir un [facette de paramètres régionaux](../standard-library/locale-class.md#facet_class) de type [collate](../standard-library/collate-class.md#collate__collate)\< CharType>. Son comportement est déterminé par la [nommé](../standard-library/locale-class.md#locale__name) paramètres régionaux `_Locname`. Chaque constructeur initialise les objets de base avec [collate](../standard-library/collate-class.md#collate__collate)\< CharType>( `_Refs`).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< paramètres régionaux>  
  
 **Namespace :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



