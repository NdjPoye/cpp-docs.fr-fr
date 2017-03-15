---
title: "Stockage local des threads (TLS) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multithreading (C++), stockage local des threads"
  - "stockage des données spécifiques aux threads"
  - "attribut de thread"
  - "stockage local des threads (C++)"
  - "threads (C++), stockage local des threads"
  - "TLS (C++)"
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Stockage local des threads (TLS)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le stockage local des threads \(TLS, Thread Local Storage\) est une méthode où chaque thread d'un processus multithread donné peut allouer des emplacements de stockage de données propres au thread.  Les données propres au thread liées de façon dynamique \(au moment de l'exécution\) sont prises en charge par le biais des API TLS \([TlsAlloc](assetId:///TlsAlloc?qualifyHint=False&autoUpgrade=True), [TlsGetValue](assetId:///TlsGetValue?qualifyHint=False&autoUpgrade=True), [TlsSetValue](assetId:///TlsSetValue?qualifyHint=False&autoUpgrade=True) et [TlsFree](assetId:///TlsFree?qualifyHint=False&autoUpgrade=True)\).  Pour plus d'informations sur l'implémentation du stockage local des threads sur Windows, consultez [Stockage local des threads \(Windows\)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686749\(v=vs.85\).aspx).  Win32 et le compilateur Visual C\+\+ prennent désormais en charge les données par thread liées statiquement \(au moment du chargement\) en plus de l'implémentation existante des API.  
  
##  <a name="_core_compiler_implementation_for_tls"></a> Implémentation du compilateur pour TLS  
 **C \+\+ 11 :**  le spécificateur de classe de stockage `thread_local` est la méthode recommandée pour spécifier le stockage local des threads pour les objets et membres de classe.  Pour plus d'informations, consultez [Classes de stockage \(C\+\+\)](../cpp/storage-classes-cpp.md#thread_local).  
  
 Visual C\+\+ fournit aussi un attribut propre à Microsoft, [thread](../cpp/thread.md) en guise de modificateur de classe de stockage étendu.  Utilisez le mot clé `__declspec` pour déclarer une variable **thread**.  Par exemple, le code suivant déclare une variable locale de thread entière et lui affecte une valeur initiale :  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
## Règles et limitations  
 Les instructions suivantes doivent être observées au moment de déclarer des variables et des objets locaux de thread liés statiquement.  Ces instructions s'appliquent à [thread](../cpp/thread.md) mais aussi dans une large mesure à [thread\_local](../cpp/storage-classes-cpp.md#thread_local) :  
  
-   L'attribut `thread` ne peut s'appliquer qu'à des déclarations et définitions de classe et de données.  Il ne peut pas être utilisé avec des définitions ou des déclarations de fonction.  Par exemple, le code suivant génère une erreur de compilation :  
  
    ```  
  
    __declspec( thread )void func();     // This will generate an error.  
    ```  
  
-   Le modificateur `thread` peut être spécifié uniquement sur les éléments de données d'étendue `static`.  Cela concerne notamment les objets de données globaux \(`static` et `extern`\), les objets statiques locaux et les membres de données statiques des classes C\+\+.  Les objets de données automatiques ne peuvent pas être déclarés avec l'attribut `thread`.  Le code suivant génère des erreurs de compilation :  
  
    ```  
  
    void func1()  
    {  
        __declspec( thread )int tls_i;            // This will generate an error.  
    }  
  
    int func2(__declspec( thread )int tls_i )    // This will generate an error.  
    {  
        return tls_i;  
    }  
    ```  
  
-   Les déclarations et la définition d'un objet local de thread doivent toutes spécifier l'attribut `thread`.  Par exemple, le code suivant génère une erreur :  
  
    ```  
    #define Thread  __declspec( thread )  
    extern int tls_i;        // This will generate an error, since the  
    int __declspec( thread )tls_i;        // declaration and definition differ.  
    ```  
  
-   L'attribut `thread` ne peut pas être utilisé comme modificateur de type.  Par exemple, le code suivant génère une erreur de compilation :  
  
    ```  
    char __declspec( thread ) *ch;        // Error  
    ```  
  
-   Dans la mesure où la déclaration d'objets C\+\+ qui utilisent l'attribut `thread` est autorisée, les deux exemples suivants sont équivalents du point de vue sémantique :  
  
    ```  
  
    __declspec( thread ) class B  
    {  
    // Code  
    } BObject;  // OK--BObject is declared thread local.  
  
    class B  
    {  
    // Code  
    };  
    __declspec( thread ) B BObject;  // OK--BObject is declared thread local.  
    ```  
  
-   L'adresse d'un objet local de thread n'est pas considérée comme étant constante, et toute expression impliquant une telle adresse n'est pas considérée comme une expression constante.  En C standard, la conséquence de ceci est l'interdiction d'utiliser l'adresse d'une variable locale de thread comme initialiseur d'un objet ou pointeur.  Par exemple, le code suivant est signalé comme une erreur par le compilateur C :  
  
    ```  
  
    __declspec( thread )int tls_i;  
    int *p = &tls_i;       //This will generate an error in C.  
    ```  
  
     Cette restriction ne s'applique pas en C\+\+.  Sachant que C\+\+ prévoit l'initialisation dynamique de tous les objets, vous pouvez initialiser un objet à l'aide d'une expression qui utilise l'adresse d'une variable locale de thread.  Il s'agit de la même procédure que pour construire des objets locaux de thread.  Par exemple, le code présenté plus haut ne génère pas d'erreur quand il est compilé en tant que fichier source C\+\+.  Notez que l'adresse d'une variable locale de thread est valide aussi longtemps qu'existe le thread d'où l'adresse a été extraite.  
  
-   Le langage C standard prévoit l'initialisation d'un objet ou d'une variable à l'aide d'une expression impliquant une auto\-référence, mais uniquement pour les objets d'étendue non statique.  Même si C\+\+ prévoit généralement l'initialisation dynamique d'objets à l'aide d'une expression impliquant une auto\-référence, ce type d'initialisation n'est pas permis avec les objets locaux de thread.  Exemple :  
  
    ```  
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++   
    int j = j;                               // OK in C++, error in C  
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++  
    ```  
  
     Notez qu'une expression `sizeof` qui inclut l'objet initialisé ne représente pas une auto\-référence et qu'elle est autorisée aussi bien en C qu'en C\+\+.  
  
     C\+\+ n'autorise pas l'initialisation dynamique des données de thread en raison des possibles futures améliorations dont pourrait bénéficier la fonctionnalité de stockage local des threads.  
  
-   Sur les systèmes d'exploitation Windows antérieurs à [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)], `__declspec`\( thread \) présente certaines limitations.  Si une DLL déclare des données ou un objet en tant que `__declspec`\( thread \), elle peut provoquer une erreur de protection si elle est chargée de façon dynamique.  Une fois chargée avec [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175), la DLL provoque une défaillance système chaque fois que le code fait référence aux données `__declspec`\( thread \).  Sachant que l'espace de variables globales d'un thread est alloué au moment de l'exécution, la taille de cet espace varie en fonction du calcul des besoins de l'application et de ceux de toutes les DLL liées statiquement.  Quand vous utilisez `LoadLibrary`, vous ne pouvez pas étendre cet espace pour tenir compte des variables locales de thread déclarées avec `__declspec`\( thread \).  Utilisez les API TLS, telles que [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801), dans votre DLL pour allouer TLS si la DLL risque d'être chargée avec `LoadLibrary`.  
  
## Voir aussi  
 [Multithreading à l'aide de C et de Win32](../parallel/multithreading-with-c-and-win32.md)   
 [Règles et limitations pour TLS](../misc/rules-and-limitations-for-tls.md)