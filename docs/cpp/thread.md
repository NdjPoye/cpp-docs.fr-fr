---
title: "thread | Microsoft Docs"
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
  - "thread"
  - "thread_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), thread"
  - "thread __declspec (mot clé)"
  - "stockage local des threads (TLS)"
  - "TLS (stockage local des threads), implémentation du compilateur"
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# thread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le modificateur de classe de stockage étendu **thread** est utilisé pour déclarer une variable locale de thread.  Pour obtenir l'équivalent portable en C\+\+11, utilisez le spécificateur de classe de stockage [thread\_local](../cpp/storage-classes-cpp.md#thread_local).  
  
## Syntaxe  
  
```  
  
__declspec( thread ) declarator  
```  
  
## Notes  
 Le stockage local des threads \(TLS\) est le mécanisme par lequel chaque thread d'un processus multithread alloue de l'espace de stockage pour les données spécifiques aux threads.  Dans les programmes multithread standard, les données sont partagées entre tous les threads d'un processus donné, alors que le stockage local des threads est le mécanisme d'allocation des données par thread.  Pour une description complète des threads, reportez\-vous à la rubrique [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Les déclarations de variables de thread locales doivent utiliser la [syntaxe à attributs étendus](../cpp/declspec.md) et le mot clé `__declspec` avec le mot clé **thread**.  Par exemple, le code suivant déclare une variable locale de thread entière et lui affecte une valeur initiale :  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
 Vous devez respecter ces indications lorsque vous déclarez des variables et des objets locaux de thread :  
  
-   Vous pouvez appliquer l'attribut de **thread** uniquement aux déclarations et définitions de classes et de données ; l'attribut de **thread** ne peut pas être utilisé sur des définitions ou déclarations de fonctions.  
  
-   L'attribut de **thread** peut perturber le [chargement différé](../build/reference/linker-support-for-delay-loaded-dlls.md) des importations de DLL**.**  
  
-   Sur les systèmes XP, `thread` peut ne pas fonctionner correctement si une DLL utilise des données \_\_declspec\(thread\) et est chargée dynamiquement via LoadLibrary.  
  
-   Vous pouvez spécifier l'attribut de **thread** uniquement pour les éléments de données ayant une durée de stockage statique.  Cela comprend les objets de données globaux \(**static** et `extern`\), les objets statiques locaux et les membres de données statiques des classes.  Vous ne pouvez pas déclarer d'objets de données automatiques à l'aide de l'attribut de **thread**.  
  
-   Vous devez utiliser l'attribut de **thread** pour la déclaration et la définition d'un objet local de thread, que la déclaration et la définition se produisent dans le même fichier ou dans des fichiers séparés.  
  
-   Vous ne pouvez pas utiliser l'attribut de **thread** en tant que modificateur de type.  
  
-   Dans la mesure où la déclaration d'objets utilisant l'attribut de **thread** est autorisée, ces deux exemples sont équivalents sur le plan sémantique :  
  
    ```  
    // declspec_thread_2.cpp  
    // compile with: /LD  
    __declspec( thread ) class B {  
    public:  
       int data;  
    } BObject;   // BObject declared thread local.  
  
    class B2 {  
    public:  
       int data;  
    };  
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.  
    ```  
  
-   Le langage C standard permet l'initialisation d'un objet ou d'une variable à l'aide d'une expression impliquant une auto\-référence, mais uniquement pour les objets d'étendue non statique.  Même si C\+\+ admet normalement l'initialisation dynamique d'un objet à l'aide d'une référence impliquant une auto\-référence, ce type d'initialisation n'est pas permis avec les objets locaux de thread.  Exemple :  
  
    ```  
    // declspec_thread_3.cpp  
    // compile with: /LD  
    #define Thread __declspec( thread )  
    int j = j;   // Okay in C++; C error  
    Thread int tls_i = sizeof( tls_i );   // Okay in C and C++  
    ```  
  
     Notez qu'une expression `sizeof` comprenant l'objet initialisé ne constitue pas une auto\-référence, et qu'elle est autorisée en C et en C\+\+.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Stockage local des threads \(TLS\)](../parallel/thread-local-storage-tls.md)