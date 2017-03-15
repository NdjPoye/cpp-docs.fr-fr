---
title: "Comment&#160;: effectuer une migration vers /clr:safe (C++/CLI) | Microsoft Docs"
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
  - "/clr (option du compilateur C++), migrer vers /clr:safe"
  - "migration (C++), assemblys vérifiables"
  - "mettre à niveau les applications Visual C++, assemblys vérifiables"
  - "assemblys vérifiables (C++), migrer vers"
ms.assetid: 75f9aae9-1dcc-448a-aa11-2d96f972f9d2
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: effectuer une migration vers /clr:safe (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ peut générer des composants vérifiables en utilisant **\/clr:safe**, ce qui contraint le compilateur à générer des erreurs pour chaque construction de code non vérifiable.  
  
## Notes  
 Les problèmes suivants génèrent des erreurs de vérifiabilité :  
  
-   Types natifs.  Même si elle n'est pas utilisée, la déclaration de classes natives, de structures, de pointeurs ou de tableaux empêche toute compilation.  
  
-   Variables globales  
  
-   Appels de fonction dans toute bibliothèque non managée, notamment les appels de fonction du Common Language Runtime  
  
-   Une fonction vérifiable ne peut pas contenir d'[static\_cast, opérateur](../cpp/static-cast-operator.md) pour l'exécution d'un downcast.  L'[static\_cast, opérateur](../cpp/static-cast-operator.md) peut être utilisé pour effectuer un cast entre des types primitifs. En revanche, pour effectuer un downcast, [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) ou un cast de style C \(implémenté en tant que [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)\) doit être utilisé.  
  
-   Une fonction vérifiable ne peut pas contenir d'[reinterpret\_cast, opérateur](../cpp/reinterpret-cast-operator.md) \(ou tout cast de style C\).  
  
-   Une fonction vérifiable ne peut pas effectuer d'opération arithmétique sur [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md).  Elle peut uniquement lui effectuer une assignation et annuler une référence à celui\-ci.  
  
-   Une fonction vérifiable peut uniquement lever ou intercepter des pointeurs vers des types référence. Par conséquent, les types valeur doivent être convertis avant d'être levés.  
  
-   Une fonction vérifiable peut uniquement appeler des fonctions vérifiables \(par exemple les appels au Common Language Runtime ne sont pas autorisés, notamment `AtEntry`\/`AtExit`, et il en est de même pour les constructeurs globaux\).  
  
-   Une classe vérifiable ne peut pas utiliser <xref:System.Runtime.InteropServices.LayoutKind>.  
  
-   En cas de génération d'un fichier EXE, une fonction principale ne peut pas déclarer tous les paramètres ; par conséquent, <xref:System.Environment.GetCommandLineArgs%2A> doit être utilisé pour récupérer des arguments de ligne de commande.  
  
-   Appel non virtuel à une fonction virtuelle.  Par exemple :  
  
    ```  
    // not_verifiable.cpp  
    // compile with: /clr  
    ref struct A {  
       virtual void Test() {}  
    };  
  
    ref struct B : A {};  
  
    int main() {  
       B^ b1 = gcnew B;  
       b1->A::Test();   // Non-virtual call to virtual function  
    }  
    ```  
  
 En outre, les mots clés suivants ne peuvent pas être employés dans du code vérifiable :  
  
-   pragmas [unmanaged](../preprocessor/managed-unmanaged.md) et [pack](../preprocessor/pack.md)  
  
-   modificateurs [naked](../cpp/naked-cpp.md) et [align](../cpp/align-cpp.md) [\_\_declspec](../cpp/declspec.md)  
  
-   [\_\_asm](../assembler/inline/asm.md)  
  
-   [\_\_based](../cpp/based-grammar.md)  
  
-   [\_\_try](../cpp/try-except-statement.md) et `__except`  
  
## Voir aussi  
 [Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md)