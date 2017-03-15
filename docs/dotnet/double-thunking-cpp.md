---
title: "Double conversion de code (thunking) (C++) | Microsoft Docs"
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
  - "/clr (option du compilateur C++), double conversion de code (thunking)"
  - "double conversions de code (thunks)"
  - "Interop (C++), double conversion de code (thunking)"
  - "interopérabilité (C++), double conversion de code (thunking)"
  - "assemblys mixtes (C++), double conversion de code (thunking)"
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Double conversion de code (thunking) (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le double médiateur \(thunking\) fait référence à la perte de performances qui peut se produire lorsqu'un appel de fonction dans un contexte managé appelle une fonction managée Visual C\+\+ et que l'exécution du programme appelle le point d'entrée natif de la fonction pour appeler la fonction managée.  Cette rubrique explique dans quel contexte le double médiateur peut survenir et comment l'éviter pour améliorer les performances.  
  
## Remarques  
 Par défaut, lors de la compilation avec **\/clr** \(et non **\/clr:pure**\), la définition d'une fonction managée provoque la génération par le compilateur d'un point d'entrée managé et d'un point d'entrée natif.  Cela permet d'appeler la fonction managée depuis des sites d'appel natifs et managés.  Toutefois, lorsqu'un point d'entrée natif existe, il peut être le point d'entrée pour tous les appels à la fonction.  Si une fonction appelante est managée, le point d'entrée natif appellera le point d'entrée managé.  En fait, deux appels sont requis pour appeler la fonction \(d'où le double médiateur\).  Par exemple, les fonctions virtuelles sont toujours appelées à travers un point d'entrée natif.  
  
 Une résolution consiste à dire au compilateur de ne pas générer de point d'entrée natif pour une fonction managée et que la fonction ne sera appelée que d'un contexte managé, à l'aide de la convention d'appel [\_\_clrcall](../cpp/clrcall.md).  
  
 De même, si vous exportez \([dllexport, dllimport](../cpp/dllexport-dllimport.md)\) une fonction managée, un point d'entrée natif est généré et toute fonction qui importe et appelle cette fonction appellera via le point d'entrée natif.  Pour éviter un double médiateur dans cette situation, n'utilisez pas de sémantique d'exportation\/importation native ; référencez simplement les métadonnées via `#using` \(voir [\#using, directive](../preprocessor/hash-using-directive-cpp.md)\).  
  
 Le compilateur a été mis à jour pour réduire la double conversion de code inutile.  Par exemple, toute fonction ayant un type managé dans sa signature \(y compris le type de retour\) sera marquée implicitement comme `__clrcall`.  Pour plus d'informations sur la double élimination de conversion de code, consultez [http:\/\/msdn.microsoft.com\/msdnmag\/issues\/05\/01\/COptimizations\/default.aspx](http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx).  
  
## Exemple  
  
### Description  
 L'exemple suivant illustre un double médiateur.  Lorsqu'il est compilé en natif \(sans **\/clr**\), l'appel à la fonction virtuelle dans `main` génère un appel au constructeur de copie de `T` et un appel au destructeur.  Un comportement similaire survient lorsque la fonction virtuelle est déclarée avec **\/clr** et `__clrcall`.  Toutefois, lorsqu'il vient d'être compilé avec **\/clr**, l'appel de fonction génère un appel au constructeur de copie mais un autre appel est effectué au constructeur de copie dû au double médiateur entre natif et managé.  
  
### Code  
  
```  
// double_thunking.cpp  
// compile with: /clr  
#include <stdio.h>  
struct T {  
   T() {  
      puts(__FUNCSIG__);  
   }  
  
   T(const T&) {  
      puts(__FUNCSIG__);  
   }  
  
   ~T() {  
      puts(__FUNCSIG__);  
   }  
  
   T& operator=(const T&) {  
      puts(__FUNCSIG__);  
      return *this;  
   }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
  
   printf("calling struct S\n");  
   pS->f(t);  
   printf("after calling struct S\n");  
}  
```  
  
### Résultat de l'exemple  
  
```  
__thiscall T::T(void)  
calling struct S  
__thiscall T::T(const struct T &)  
__thiscall T::T(const struct T &)  
__thiscall T::~T(void)  
__thiscall T::~T(void)  
after calling struct S  
__thiscall T::~T(void)  
```  
  
## Exemple  
  
### Description  
 L'exemple précédent a montré l'existence d'un double médiateur.  Cet exemple montre son effet.  La boucle `for` appelle la fonction virtuelle et le programme rapporte le temps d'exécution.  Le temps le plus long rapporté correspond à une compilation du programme avec **\/clr**.  Le temps le plus rapide rapporté correspond à une compilation sans **\/clr** ou lorsque la fonction virtuelle est déclarée avec `__clrcall`.  
  
### Code  
  
```  
// double_thunking_2.cpp  
// compile with: /clr  
#include <time.h>  
#include <stdio.h>   
  
#pragma unmanaged  
struct T {  
   T() {}  
   T(const T&) {}  
   ~T() {}  
   T& operator=(const T&) { return *this; }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
   clock_t start, finish;  
   double  duration;  
   start = clock();  
  
   for ( int i = 0 ; i < 1000000 ; i++ )  
      pS->f(t);  
  
   finish = clock();  
   duration = (double)(finish - start) / (CLOCKS_PER_SEC);  
   printf( "%2.1f seconds\n", duration );  
   printf("after calling struct S\n");  
}  
```  
  
### Résultat de l'exemple  
  
```  
4.2 seconds  
after calling struct S  
```  
  
## Voir aussi  
 [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)