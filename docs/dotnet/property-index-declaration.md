---
title: "D&#233;claration de l&#39;index de la propri&#233;t&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "indexeurs par défaut"
  - "valeurs par défaut, indexeurs"
  - "propriétés indexées, C++"
  - "indexeurs"
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;claration de l&#39;index de la propri&#233;t&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La syntaxe servant à déclarer une propriété indexée a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 La prise en charge par le langage des Extensions managées des propriétés indexées présente deux défauts principaux. Le premier est son incapacité à fournir une mise en indice de niveau de classe ; autrement dit, toutes les propriétés indexées doivent être nommées, et il n'y a donc, par exemple, aucun moyen de fournir un opérateur managé de mise en indice qui puisse être directement appliqué à un objet de classe `Vector` ou `Matrix`.  Le second défaut, moins problématique, est qu'il est visuellement difficile de distinguer une propriété d'une propriété indexée, le nombre de paramètres étant la seule indication.  Enfin, les propriétés indexées souffrent des mêmes problèmes que les propriétés non indexées \- les accesseurs ne sont pas traités comme une unité atomique, mais séparés dans des méthodes individuelles.  Par exemple :  
  
```  
public __gc class Vector;  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value);  
   __property float get_Item( int r, int c );  
  
   __property void set_Row( int r, Vector* value );  
   __property Vector* get_Row( int r );  
};  
```  
  
 Comme vous pouvez le constater, les indexeurs ne se distinguent que par les paramètres supplémentaires qui spécifient un index à deux ou à une seule dimension.  Dans la nouvelle syntaxe, les indexeurs se distinguent par les crochets \(\[,\]\) qui suivent le nom de l'indexeur et qui indiquent le nombre et le type de chaque index :  
  
```  
public ref class Vector {};  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 Dans la nouvelle syntaxe, pour indiquer un indexeur de niveau de classe qui peut être appliqué directement aux objets de la classe, le mot clé `default` est réutilisé pour se substituer à un nom explicite.  Par exemple :  
  
```  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //  
   //     Matrix mat …  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer …  
  
   property float default [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 Dans la nouvelle syntaxe, lorsque la propriété indexée par défaut est spécifiée, les deux noms suivants sont réservés : `get_Item` et `set_Item`.  En effet, il s'agit des noms sous\-jacents générés pour la propriété indexée par défaut.  
  
 Notez qu'il n'y a aucune syntaxe d'index simple analogue à la syntaxe de propriété simple.  
  
## Voir aussi  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Comment : utiliser des propriétés indexées](../misc/how-to-use-indexed-properties.md)