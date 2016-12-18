---
title: "Restrictions de /clr | Microsoft Docs"
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
  - "/clr (option du compilateur C++), restrictions"
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Restrictions de /clr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Notez les restrictions suivantes concernant l'utilisation de **\/clr** :  
  
-   Dans un gestionnaire d'exceptions structuré, l'utilisation de `_alloca` lors de la compilation avec **\/clr** présente des restrictions.  Pour plus d'informations, consultez [\_alloca](../../c-runtime-library/reference/alloca.md).  
  
-   L'utilisation de vérifications des erreurs à l'exécution n'est pas valide avec **\/clr**.  Pour plus d'informations, consultez [Vérifications des erreurs à l'exécution](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md).  
  
-   Lorsque **\/clr** est utilisé pour compiler un programme qui n'utilise que la syntaxe C\+\+ standard, les indications suivantes s'appliquent à l'utilisation de l'assembleur inline :  
  
    -   Le code assembleur inline, qui suppose la connaissance de la disposition de la pile native, des conventions d'appel en dehors de la fonction en cours ou d'autres informations de bas niveau concernant l'ordinateur, peut échouer si cette connaissance est appliquée au frame de pile pour une fonction managée.  Les fonctions contenant du code assembleur inline sont générées en tant que fonctions non managées, comme si elles étaient placées dans un module distinct compilé sans l'option **\/clr**.  
  
    -   Le code assembleur inline dans les fonctions qui passent des paramètres de fonction construits par copie n'est pas pris en charge.  
  
-   Les [fonctions vprintf](../../c-runtime-library/vprintf-functions.md) ne peuvent pas être appelées à partir d'un programme compilé avec **\/clr**.  
  
-   Le modificateur [naked](../../cpp/naked-cpp.md) [\_\_declspec](../../cpp/declspec.md) est ignoré sous \/clr.  
  
-   La fonction de transcodage, définie par un appel à [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md), agit uniquement sur les interceptions dans le code non managé.  Pour plus d'informations, consultez [Exception Handling](../../windows/exception-handling-cpp-component-extensions.md).  
  
-   La comparaison des pointeurs fonction n'est pas autorisée sous **\/clr**.  
  
-   L'utilisation de fonctions qui ne sont pas entièrement prototypées n'est pas autorisée sous **\/clr**.  
  
-   Les options du compilateur suivantes ne sont pas prises en charge avec **\/clr**:  
  
    -   **\/EHsc** et **\/EHs** \(**\/clr** implique **\/EHa**\) ; consultez [\/EH \(Modèle de gestion des exceptions\)](../../build/reference/eh-exception-handling-model.md)\)  
  
    -   **\/fp:strict** et **\/fp:except** \(consultez [\/fp \(Spécifier le comportement de virgule flottante\)](../../build/reference/fp-specify-floating-point-behavior.md)\)  
  
    -   [\/Zd](../../build/reference/z7-zi-zi-debug-information-format.md)  
  
    -   [\/Gm](../../build/reference/gm-enable-minimal-rebuild.md)  
  
    -   [\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)  
  
    -   [\/RTC](../../build/reference/rtc-run-time-error-checks.md)  
  
    -   **\/ZI**  
  
-   La combinaison de la définition du préprocesseur `_STATIC_CPPLIB` \(`/D_STATIC_CPPLIB`\) et de l'option du compilateur **\/clr** ou **\/clr:pure** n'est pas prise en charge.  Cela est dû au fait que la définition provoquerait la liaison de votre application à la bibliothèque C\+\+ standard multithread statique, qui n'est pas prise en charge.  Pour plus d'informations, consultez la rubrique [\/MD, \/MT, \/LD \(Utiliser la bibliothèque Runtime\)](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
-   [\/J](../../build/reference/j-default-char-type-is-unsigned.md) n'est pas pris en charge avec **\/clr:safe** ou **\/clr:pure**.  
  
-   Les bibliothèques ATL et MFC ne sont pas prises en charge par la compilation en mode pur \(**\/clr:pure**\).  Vous pouvez utiliser **\/clr:pure** avec la bibliothèque C\+\+ standard et le CRT si vous compilez également avec **\/MD** ou **\/MDd**.  
  
-   En cas d'utilisation de **\/Zi** avec **\/clr**, vous constaterez certaines conséquences sur les performances.  Pour plus d'informations, consultez [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
-   Le passage d'un caractère large à une routine de sortie du .NET Framework sans spécification de [\/Zc:wchar\_t](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) ou sans casting du caractère en `__wchar_t` fait apparaître la sortie en tant que valeur `unsigned short int`.  Par exemple :  
  
    ```  
    Console::WriteLine(L' ')              // Will output 32.  
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.  
    ```  
  
-   L'option [\/GS](../../build/reference/gs-buffer-security-check.md) est ignorée lors de la compilation avec **\/clr**, sauf si une fonction se trouve sous `#pragma` [unmanaged](../../preprocessor/managed-unmanaged.md) ou si la fonction doit être compilée à l'état natif, auquel cas le compilateur générera l'avertissement C4793, qui est désactivé par défaut.  
  
-   Consultez [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) pour connaître les conditions de signature d'une application managée.  
  
-   Les applications compilées avec **\/openmp** et **\/clr** ne peuvent être exécutées que dans un processus appdomain unique.  Pour plus d'informations, consultez [\/openmp \(Activer la prise en charge OpenMP 2.0\)](../../build/reference/openmp-enable-openmp-2-0-support.md).  
  
-   Les fonctions qui prennent un nombre variable d'arguments \(varargs\) sont générées en tant que fonctions natives.  Tous les types de données managés dans la position d'arguments variables sont marshalés en type natif.  Notez que les types <xref:System.String?displayProperty=fullName> sont en fait des chaînes à caractère large, mais ils sont marshalés en chaînes codées sur un octet.  Ainsi, si un spécificateur printf est %S \(wchar\_t\*\), il est plutôt marshalé en une chaîne %s.  
  
-   Lors de l'utilisation de la macro va\_arg, vous pouvez obtenir des résultats inattendus en cas de compilation avec **\/clr:pure**.  Pour plus d'informations, consultez [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md).  
  
-   Si votre application passe un argument de type [va\_list](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) à une fonction déclarée de façon à prendre un [nombre variable d'arguments](../../misc/variable-argument-lists.md), et que votre application est compilée avec **\/clr:pure**, le CLR lève <xref:System.NotSupportedException>.  Si **\/clr**  est utilisé à la place, les fonctions affectées sont compilées en code natif et s'exécutent correctement.  Si **\/clr:safe** est utilisé, un diagnostic des erreurs est émis.  
  
-   Vous ne devez appeler, à partir du code managé, aucune fonction parcourant la pile pour obtenir des informations sur les paramètres \(arguments de fonction\) ; la couche P\/Invoke repousse ces informations plus bas dans la pile.  Par exemple, ne compilez pas de code proxy\/stub avec **\/clr**.  
  
-   Les fonctions seront compilées en code managé chaque fois que c'est possible, mais toutes les constructions C\+\+ ne peuvent être converties en code managé.  Cette détermination s'effectue fonction par fonction.  Si une partie d'une fonction ne peut pas être convertie en code managé, la fonction entière est plutôt convertie en code natif.  Les cas suivants empêchent le compilateur de générer du code managé.  
  
    -   Thunks générés par le compilateur ou fonctions d'assistance.  Des thunks natifs sont générés pour tout appel de fonction à l'aide d'un pointeur fonction, y compris les appels de fonction virtuelle.  
  
    -   Fonctions qui appellent `setjmp` ou `longjmp`.  
  
    -   Fonctions qui utilisent certaines routines intrinsèques pour manipuler directement des ressources d'ordinateur.  Par exemple, l'utilisation de `__enable` ainsi que de `__disable`, `_ReturnAddress` et `_AddressOfReturnAddress` ou d'éléments intrinsèques multimédia produisent tous du code natif.  
  
    -   Fonctions qui suivent la directive `#pragma unmanaged`. \(Notez que l'inverse, `#pragma managed`, est également pris en charge.\)  
  
    -   Une fonction contenant des références à des types alignés, c'est\-à\-dire à des types déclarés à l'aide de `__declspec(align(...))`.  
  
-   Vous ne pouvez pas utiliser les classes [Prise en charge COM du compilateur](../../cpp/compiler-com-support.md) avec **\/clr:pure** ou **\/clr:safe**.  
  
## Voir aussi  
 [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)