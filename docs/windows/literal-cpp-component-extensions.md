---
title: "literal (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "literal"
  - "literal_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "literal keyword [C++]"
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# literal (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une variable \(membre de données\) est marqué comme `literal` dans une compilation **\/clr** revient au format natif d'une variable `static const`.  
  
## Toutes les plateformes  
 **Remarques**  
  
 \(Aucune note de cette fonctionnalité de langage ne s'applique à tous les runtimes.\)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Remarques**  
  
 \(Aucune note de cette fonctionnalité de langage ne s'applique qu'au Windows Runtime.\)  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
  
## Notes  
 Un membre de données marqué comme `literal`doit être initialisé lorsqu'elle est déclarée et la valeur doit être une intégrale, une énumération, ou un type chaîne constante.  La conversion du type de l'expression d'initialisation vers le type du membre de données const statique ne doit pas avoir une conversion définie par l'utilisateur.  
  
 Aucune mémoire n'est allouée pour le champ littéral au moment de l'exécution ; le compilateur insère uniquement sa valeur dans les métadonnées pour la classe.  
  
 Une variable marquée par `static const` n'est pas disponible dans les métadonnées pour d'autres compilateurs.  
  
 Pour plus d’informations, consultez [Statique](../misc/static-cpp.md) et [const](../cpp/const-cpp.md).  
  
 `literal` est un mot clé contextuel.  Pour plus d'informations, consultez [Mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## Exemple  
 Cet exemple montre qu'une variable `literal` implique `static`.  
  
```  
// mcppv2_literal.cpp  
// compile with: /clr  
ref struct X {  
   literal int i = 4;  
};  
  
int main() {  
   int value = X::i;  
}  
```  
  
## Exemple  
 L'exemple suivant montre l'effet du littéral dans les métadonnées :  
  
```  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 Notez la différence dans les métadonnées de `sc` et `lit`: la directive `modopt` est appliquée à `sc`, ce qui signifie qu'elle peut être ignorée par d'autres compilateurs.  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## Exemple  
 L'exemple suivant, créé en c, référence les métadonnées créées dans l'exemple précédent et affiche l'effet de `literal` et des variables `static const`:  
  
```  
// mcppv2_literal3.cs  
// compile with: /reference:mcppv2_literal2.dll  
// A C# program  
class B {  
   public static void Main() {  
      // OK  
      System.Console.WriteLine(A.lit);  
      System.Console.WriteLine(A.sc);  
  
      // C# does not enforce C++ const  
      A.sc = 9;  
      System.Console.WriteLine(A.sc);  
  
      // C# enforces const for a literal  
      A.lit = 9;   // CS0131  
  
      // you can assign a C++ literal variable to a C# const variable  
      const int i = A.lit;  
      System.Console.WriteLine(i);  
  
      // but you cannot assign a C++ static const variable  
      // to a C# const variable  
      const int j = A.sc;   // CS0133  
      System.Console.WriteLine(j);  
   }  
}  
```  
  
## Conditions requises  
 Option du compilateur : **\/clr**  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)