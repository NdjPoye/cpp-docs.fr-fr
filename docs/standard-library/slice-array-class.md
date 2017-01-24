---
title: "slice_array, classe | Microsoft Docs"
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
  - "slice_array"
  - "valarray/std::slice_array"
  - "std.slice_array"
  - "std::slice_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "slice_array (classe)"
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# slice_array, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe de modèle interne et connexe qui prend en charge les objets de secteur en fournissant des opérations entre les tables de sous\-ensemble défini par la tranche d'un valarray.  
  
## Syntaxe  
  
```  
template<class Type>  
   class slice_array : public slice {  
public:  
   typedef Type value_type;  
   void operator=(  
      const valarray<Type>& x  
   ) const;  
   void operator=(  
      const Type& x  
   ) const;  
   void operator*=(  
      const valarray<Type>& x  
   ) const;  
   void operator/=(  
      const valarray<Type>& x  
   ) const;  
   void operator%=(  
      const valarray<Type>& x  
   ) const;  
   void operator+=(  
      const valarray<Type>& x  
   ) const;  
   void operator-=(  
      const valarray<Type>& x  
   ) const;  
   void operator^=(  
      const valarray<Type>& x  
   ) const;  
   void operator&=(  
      const valarray<Type>& x  
   ) const;  
   void operator|=(  
      const valarray<Type>& x  
   ) const;  
   void operator<<=(  
      const valarray<Type>& x  
   ) const;  
   void operator>>=(  
      const valarray<Type>& x  
   ) const;  
// The rest is private or implementation defined  
}  
```  
  
## Notes  
 La classe décrit un objet qui contient une référence à un objet de la classe [valarray](../standard-library/valarray-class.md)**\<Type\>**, avec un objet de la classe [secteur](../standard-library/slice-class.md), qui décrit la séquence d'éléments pour sélectionner l'objet de **valarray\<Type\>**.  
  
 La classe de modèle est créée indirectement par certaines opérations de valarray et ne peut pas être utilisée directement dans le programme.  Une classe de modèle interne et connexe utilisée par l'opérateur souscrit de procédez comme suit :  
  
 `slice_array`\<**Type**\>`valarray`\<**Type**::`operator[]` \(`slice`\).  
  
 Vous construisez un objet de **slice\_array\<Type\>** uniquement en entrant une expression de format [va&#91;sl&#93;](../Topic/valarray::operator.md), pour un **sl** de valarray **va**.  Les fonctions membres de la classe slice\_array se comportent ensuite comme les signatures de la fonction correspondantes définies pour **valarray\<Type\>**, mais que seule la séquence d'éléments sélectionnés est affectée.  La séquence contrôlée par le slice\_array est définie par les trois paramètres dans le constructeur de secteur, de l'index du premier élément dans la tranche, le nombre d'éléments, ainsi que la distance entre les éléments.  Un slice\_array de valarray **va** déclaré par **va**\[`slice`\(2, 5, 3\)\] sélectionne les éléments dont les index 2, 5, 8, 11 et 14 de **va**.  Les index doivent être valides pour que la procédure est pas valide.  
  
## Exemple  
 Consultez l'exemple de [slice::slice](../Topic/slice::slice.md) pour obtenir un exemple de la façon dont déclarer et utiliser un slice\_array.  
  
## Configuration requise  
 **Header:**\<valarray\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)