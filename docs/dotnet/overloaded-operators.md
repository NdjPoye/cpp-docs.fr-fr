---
title: "Op&#233;rateurs surcharg&#233;s | Microsoft Docs"
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
  - "surcharge d'opérateur, dans une classe CLR"
  - "opérateurs (C++), surcharger"
ms.assetid: 30391426-afe7-4497-bf22-e4816c1e48c8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs surcharg&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La surcharge d'opérateur a été considérablement modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Dans la déclaration d'un type référence, par exemple, au lieu d'utiliser la syntaxe `operator+` native, il faut inscrire explicitement le nom interne sous\-jacent de l'opérateur – ici, `op_Addition`.  En outre, l'appel d'un opérateur doit être appelé explicitement à travers ce nom, ce qui annule les deux avantages principaux de la surcharge d'opérateur : \(a\) une syntaxe intuitive et \(b\) la possibilité de mélanger les types nouveaux et les types existants.  Par exemple :  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
   static Vector* op_Addition( const Vector*, const Vector* );  
   static Vector* op_Subtraction( const Vector*, const Vector* );  
};  
  
int main()  
{  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc1 = Vector::op_Addition( pa, pb );  
   Vector *pc2 = Vector::op_Subtraction( pa, pc1 );  
   Vector *pc3 = Vector::op_Division( pc1, pc2->x );  
  
   if ( Vector::op_Equality( pc1, pc2 ))  
      ;  
}  
```  
  
 Dans la nouvelle syntaxe, le programmeur C\+\+ natif retrouve ses habitudes, à la fois dans la déclaration et dans l'utilisation des opérateurs statiques.  Voici la traduction de la classe `Vector` dans la nouvelle syntaxe :  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
   static Vector^ operator +( const Vector^, const Vector^ );  
   static Vector^ operator -( const Vector^, const Vector^ );  
};  
  
int main()  
{  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475,4.8916,-1.23 );  
  
   Vector^ pc1 = pa + pb;  
   Vector^ pc2 = pa - pc1;  
   Vector^ pc3 = pc1 / pc2->x;  
  
   if ( pc1 == pc2 )  
      ;  
}  
```  
  
## Voir aussi  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)