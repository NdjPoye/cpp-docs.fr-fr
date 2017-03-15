---
title: "gslice_array, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::gslice_array"
  - "gslice_array"
  - "valarray/std::gslice_array"
  - "std.gslice_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gslice_array (classe)"
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# gslice_array, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe de modèle interne et connexe qui prend en charge la coupe général objets en fournissant des opérations entre les tables de sous\-ensemble défini par la coupe générales d'un valarray.  
  
## Syntaxe  
  
```  
template<class Type>  
   class gslice_array : public gsplice {  
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
 La classe décrit un objet qui contient une référence à un objet **va** de la classe [valarray](../standard-library/valarray-class.md)**\<Type\>**, avec un objet **gs** de la classe [gslice](../standard-library/gslice-class.md) qui décrit la séquence d'éléments pour sélectionner l'objet de **valarray\<Type\>**.  
  
 Vous construisez un objet de **gslice\_array\<Type\>** uniquement en entrant une expression de format [devient &#91;gs&#93;](../Topic/valarray::operator.md).  Les fonctions membres de la classe gslice\_array se comportent ensuite comme les signatures de la fonction correspondantes définies pour **valarray\<Type\>**, mais que seule la séquence d'éléments sélectionnés est affectée.  
  
 La classe de modèle est créée indirectement par certaines opérations de valarray et ne peut pas être utilisée directement dans le programme.  Une classe de modèle connexe interne à la place est utilisée par l'opérateur souscrit de procédez comme suit :  
  
 ::\<`operator[]` \> \(\<**const**\>**gslice&**\) d'`gslice_array`**Type** `valarray`**Type**.  
  
 Vous construisez un objet de **gslice\_array\<Type\>** uniquement en entrant une expression de format **va\[gsl\]**, pour un **gsl** de valarray **va**.  Les fonctions membres de la classe gslice\_array se comportent ensuite comme les signatures de la fonction correspondantes définies pour **valarray\<Type\>**, mais que seule la séquence d'éléments sélectionnés est affectée.  La séquence contrôlée par le gslice\_array est définie par les trois paramètres dans le constructeur de secteur, de l'index du premier élément de la première tranche, le nombre d'éléments dans chaque secteur, et la distance entre les éléments dans chaque secteur.  
  
 Dans l'exemple ci\-dessous :  
  
```  
const size_t lv[] = {2, 3};  
const size_t dv[] = {7, 2};  
const valarray<size_t> len(lv, 2), str(dv, 2);  
// va[gslice(3, len, str)] selects elements with  
//   indices 3, 5, 7, 10, 12, 14  
```  
  
 Les index doivent être valides pour que la procédure est pas valide.  
  
## Exemple  
 Consultez l'exemple de [gslice::gslice](../Topic/gslice::gslice.md) pour obtenir un exemple de la façon dont déclarer et utiliser un slice\_array.  
  
## Configuration requise  
 **Header:**\<valarray\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)