---
title: "codecvt_base, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "codecvt_base"
  - "xlocale/std::codecvt_base"
  - "std.codecvt_base"
  - "std::codecvt_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_base (classe)"
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# codecvt_base, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe de base pour la classe de codecvt utilisée pour définir un type d'énumération référencé comme **result**, utilisée comme type de retour pour les fonctions membres de la facette indiquent le résultat d'une conversion.  
  
## Syntaxe  
  
```  
class codecvt_base : public locale::facet {  
public:  
    enum result {ok, partial, error, noconv};  
    codecvt_base(  
        size_t _Refs = 0  
);  
    bool always_noconv() const;  
    int max_length() const;  
    int encoding() const;  
    ~codecvt_base()  
protected:  
    virtual bool do_always_noconv() const;  
    virtual int do_max_length() const;  
    virtual int do_encoding() const;  
};  
```  
  
## Notes  
 La classe décrit un ensemble commun d'énumération de toutes les spécialisations de classe de modèle [codecvt](../standard-library/codecvt-class.md).  Le résultat de l'énumération décrit les valeurs de retour possibles d'[do\_in](../Topic/codecvt::do_in.md) ou d'[do\_out](../Topic/codecvt::do_out.md):  
  
-   **ok** si la conversion entre les encodages de caractères internes et externes réussit.  
  
-   **partial** si la destination n'est pas assez grande pour la conversion réussisse.  
  
-   **erreur** si la séquence source est mal formée.  
  
-   **noconv** si la fonction n'effectue aucune conversion.  
  
## Configuration requise  
 paramètres régionaux \<de**En\-tête :** \>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)