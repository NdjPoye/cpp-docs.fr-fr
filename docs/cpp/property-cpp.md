---
title: "property (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "property_cpp"
  - "Property"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), propriété"
  - "property __declspec (mot clé)"
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# property (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Cet attribut peut être appliqué à des « données membres virtuelles » non statiques dans une définition de classe ou de structure.  Le compilateur traite ces « données membres virtuelles » comme des données membres en changeant leurs références en appels de fonction.  
  
## Syntaxe  
  
```  
  
      __declspec( property( get=get_func_name ) ) declarator  
__declspec( property( put=put_func_name ) ) declarator  
__declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## Notes  
 Lorsque le compilateur détecte une donnée membre déclarée avec cet attribut à droite d'un opérateur de sélection de membres \(« **.** » ou « **\-\>** »\), il convertit l'opération en fonction **get** ou **put**, selon que cette expression est une l\-value ou une r\-value.  Dans les contextes plus complexes, tels que « `+=` », une réécriture est effectuée en exécutant à la fois **get** et **put**.  
  
 Cet attribut peut également être utilisé dans la déclaration d'un tableau vide dans une définition de classe ou de structure.  Par exemple :  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 L'instruction ci\-dessus indique que `x[]` peut être utilisé avec un ou plusieurs index de tableau.  Dans ce cas, `i=p->x[a][b]` est converti en `i=p->GetX(a, b)` et `p->x[a][b] = i` est converti en `p->PutX(a, b, i);`  
  
 **FIN de la section spécifique à Microsoft**  
  
## Exemple  
  
```  
// declspec_property.cpp  
struct S {  
   int i;  
   void putprop(int j) {   
      i = j;  
   }  
  
   int getprop() {  
      return i;  
   }  
  
   __declspec(property(get = getprop, put = putprop)) int the_prop;  
};  
  
int main() {  
   S s;  
   s.the_prop = 5;  
   return s.the_prop;  
}  
```  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)