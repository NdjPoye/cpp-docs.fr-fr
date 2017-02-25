---
title: "type_info, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "type_info"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classe type_info"
  - "type_info (classe)"
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# type_info, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe **type\_info** décrit les informations de type générées à l'intérieur du programme par le compilateur.  Les objets de cette classe stockent efficacement un pointeur dans un nom pour le type.  La classe **type\_info** stocke également une valeur encodée appropriée pour comparer deux types afin de connaître l'égalité ou l'ordre de classement.  Les règles d'encodage et la séquence de classement pour les types ne sont pas spécifiées et peuvent différer entre les programmes.  
  
 Le fichier d'en\-tête \<`typeinfo>` doit être inclus afin d'utiliser la classe **type\_info**.  L'interface pour la classe **type\_info** est :  
  
```  
class type_info {  
public:  
    virtual ~type_info();  
    size_t hash_code() const  
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;  
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;  
    _CRTIMP_PURE int before(const type_info& rhs) const;  
    _CRTIMP_PURE const char* name() const;  
    _CRTIMP_PURE const char* raw_name() const;  
};  
```  
  
 Vous ne pouvez pas instancier des objets de la classe **type\_info** directement, car la classe a un seul constructeur de copie privé.  La seule façon de construire un objet **type\_info** \(temporaire\) consiste à utiliser l'opérateur [typeid](../cpp/typeid-operator.md).  Comme l'opérateur d'assignation est également privé, vous ne pouvez pas copier ou assigner des objets de classe **type\_info**.  
  
 **type\_info::hash\_code** définit une fonction de hachage appropriée pour mapper des valeurs de type **typeinfo** pour une distribution des valeurs d'index.  
  
 Les opérateurs `==` et `!=` peuvent être utilisés pour comparer l'égalité et l'inégalité avec d'autres objets **type\_info**, respectivement.  
  
 Il n'existe aucun lien entre l'ordre de classement des types et les relations d'héritage.  Utilisez la fonction membre **type\_info::before** pour déterminer la séquence de classement des types.  Il n'existe aucune garantie que **type\_info::before** génère le même résultat dans des programmes différents ou même différentes exécutions du même programme.  Ainsi, **type\_info::before** est similaire à l'opérateur address\-of **\(&\)**.  
  
 La fonction membre **type\_info::name** retourne **const char\*** à une chaîne terminée par le caractère NULL représentant le nom explicite du type.  La mémoire désignée est mise en cache et ne doit jamais être directement libérée.  
  
 La fonction membre **type\_info::raw\_name** retourne **const char\*** à une chaîne terminée par le caractère NULL représentant le nom décoré du type d'objet.  Le nom est réellement stocké sous sa forme décorée pour économiser de l'espace.  Par conséquent, cette fonction est plus rapide que **type\_info::name** car elle n'a pas besoin de supprimer la décoration du nom.  La chaîne retournée par la fonction **type\_info::raw\_name** est utile dans les opérations de comparaison mais n'est pas lisible.  Si vous avez besoin d'une chaîne explicite, utilisez la fonction **type\_info::name** à la place.  
  
 Les informations de type sont générées pour les classes polymorphes uniquement si l'option du compilateur [\/GR \(Activer les informations de type au moment de l'exécution\)](../build/reference/gr-enable-run-time-type-information.md) est spécifiée.  
  
## Voir aussi  
 [Informations de type au moment de l'exécution](../cpp/run-time-type-information.md)