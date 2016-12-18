---
title: "Macros pr&#233;d&#233;finies | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_VER"
  - "__ATOM__"
  - "__AVX__"
  - "__AVX2__"
  - "_CHAR_UNSIGNED"
  - "__CLR_VER"
  - "_CONTROL_FLOW_GUARD"
  - "__COUNTER__"
  - "__cplusplus"
  - "__cplusplus_cli"
  - "__cplusplus_winrt"
  - "_CPPRTTI"
  - "_CPPUNWIND"
  - "__DATE__"
  - "_DEBUG"
  - "_DLL"
  - "__FILE__"
  - "__FUNCDNAME__"
  - "__FUNCSIG__"
  - "__FUNCTION__"
  - "_INTEGRAL_MAX_BITS"
  - "_ISO_VOLATILE"
  - "_KERNEL_MODE"
  - "__LINE__"
  - "_M_AMD64"
  - "_M_ARM"
  - "_M_ARM_ARMV7VE"
  - "_M_ARM_FP"
  - "_M_ARM64"
  - "_M_CEE"
  - "_M_CEE_PURE"
  - "_M_CEE_SAFE"
  - "_M_FP_EXCEPT"
  - "_M_FP_FAST"
  - "_M_FP_PRECISE"
  - "_M_FP_STRICT"
  - "_M_IX86"
  - "_M_IX86_FP"
  - "_M_X64"
  - "_MANAGED"
  - "_MFC_VER"
  - "_MSC_BUILD"
  - "_MSC_EXTENSIONS"
  - "_MSC_FULL_VER"
  - "_MSC_VER"
  - "_MSVC_LANG"
  - "__MSVC_RUNTIME_CHECKS"
  - "_MT"
  - "_NATIVE_WCHAR_T_DEFINED"
  - "_NO_SIZED_DEALLOCATION"
  - "_OPENMP"
  - "_PREFAST_"
  - "_RESUMABLE_FUNCTIONS_SUPPORTED"
  - "_RTC_CONVERSION_CHECKS_ENABLED"
  - "__STDC__"
  - "__STDC_HOSTED__"
  - "__STDCPP_THREADS__"
  - "__TIME__"
  - "__TIMESTAMP__"
  - "__VA_ARGS__"
  - "_VC_NODEFAULTLIB"
  - "_WCHAR_T_DEFINED"
  - "_WIN32"
  - "_WIN64"
  - "_WINRT_DLL"
  - "__func__"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "horodateurs, la macro de préprocesseur"
  - "compilateur CL.exe, numéro de version"
  - "numéros de version, le compilateur C/C++ (cl.exe)"
  - "macros, C++ prédéfinies"
  - "macros de préprocesseur,"
  - "macros prédéfinies"
  - "_ATL_VER (macro)"
  - "Macros __ATOM__"
  - "__AVX__ (macro)"
  - "__AVX2__ (macro)"
  - "_CHAR_UNSIGNED (macro)"
  - "__CLR_VER (macro)"
  - "Macros _CONTROL_FLOW_GUARD"
  - "__COUNTER__ (macro)"
  - "__cplusplus (macro)"
  - "__cplusplus_cli (macro)"
  - "__cplusplus_winrt (macro)"
  - "_CPPRTTI (macro)"
  - "_CPPUNWIND (macro)"
  - "__DATE__ (macro)"
  - "_DEBUG (macro)"
  - "_DLL (macro)"
  - "__FILE__ (macro)"
  - "__FUNCDNAME__ (macro)"
  - "__FUNCSIG__ (macro)"
  - "__FUNCTION__ (macro)"
  - "_INTEGRAL_MAX_BITS (macro)"
  - "Macros _ISO_VOLATILE"
  - "Macros _KERNEL_MODE"
  - "__LINE__ (macro)"
  - "_M_AMD64 (macro)"
  - "_M_ARM (macro)"
  - "Macros _M_ARM_ARMV7VE"
  - "_M_ARM_FP (macro)"
  - "Macros _M_ARM64"
  - "_M_CEE (macro)"
  - "_M_CEE_PURE (macro)"
  - "_M_CEE_SAFE (macro)"
  - "Macros _M_FP_EXCEPT"
  - "Macros _M_FP_FAST"
  - "Macros _M_FP_PRECISE"
  - "Macros _M_FP_STRICT"
  - "_M_IX86 (macro)"
  - "_M_IX86_FP (macro)"
  - "_M_X64 (macro)"
  - "_MANAGED (macro)"
  - "_MFC_VER (macro)"
  - "_MSC_BUILD (macro)"
  - "_MSC_EXTENSIONS (macro)"
  - "_MSC_FULL_VER (macro)"
  - "_MSC_VER (macro)"
  - "Macros _MSVC_LANG"
  - "__MSVC_RUNTIME_CHECKS (macro)"
  - "_MT (macro)"
  - "_NATIVE_WCHAR_T_DEFINED (macro)"
  - "Macros _NO_SIZED_DEALLOCATION"
  - "_OPENMP (macro)"
  - "Macros _PREFAST_"
  - "Macros _RESUMABLE_FUNCTIONS_SUPPORTED"
  - "Macros _RTC_CONVERSION_CHECKS_ENABLED"
  - "__STDC__ (macro)"
  - "Macros __STDC_HOSTED__"
  - "Macros __STDCPP_THREADS__"
  - "__TIME__ (macro)"
  - "__TIMESTAMP__ (macro)"
  - "Macros __VA_ARGS__"
  - "_VC_NODEFAULTLIB (macro)"
  - "_WCHAR_T_DEFINED (macro)"
  - "_WIN32 (macro)"
  - "_WIN64 (macro)"
  - "Macros _WINRT_DLL"
  - "identificateur de __func__"
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
caps.latest.revision: 75
caps.handback.revision: 75
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Macros pr&#233;d&#233;finies
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur Visual C++ prédéfinit certaines macros de préprocesseur, selon la langue (C ou C++), la cible de compilation et les options de compilateur choisie.  
  
 Visual C++ prend en charge les macros de préprocesseur prédéfinies requis spécifiés par la norme ANSI/ISO C99 et la norme ISO C ++ 14 standard. L’implémentation prend également en charge plusieurs macros préprocesseur plus spécifiques à Microsoft. Certaines macros sont définies uniquement pour les environnements de génération spécifique ou les options du compilateur. Sauf indication, les macros sont définies dans une unité de traduction comme si elles étaient spécifiées en tant que **/D** arguments de l’option du compilateur. Lorsque défini, les macros sont développées avec les valeurs spécifiées par le préprocesseur avant la compilation. Les macros prédéfinies ne prennent pas d’arguments et ne peut pas être redéfinis.  
  
## <a name="standard-predefined-identifier"></a>Identificateur prédéfini standard  
 Le compilateur prend en charge cet identificateur prédéfini spécifié par la norme ISO C99 et ISO C ++ 11.  
  
-   **__func\_\_** le nom non qualifié et de la fonction englobante comme fonction-local `static``const` tableau de `char`.  
  
    ```cpp  
    void example(){  
        printf("%s\n", __func__);  
    } // prints "example"  
    ```  
  
## <a name="standard-predefined-macros"></a>Macros prédéfinies standards  
 Le compilateur prend en charge ces macros prédéfinies spécifiés par l’ISO C99 et C ++ 14 normes ISO.  
  
-   **__cplusplus** définie comme une valeur littérale entière lorsque l’unité de traduction est compilée en tant que C++. Sinon, non défini.  
  
-   **__DATE\_\_** la date de compilation du fichier source actuel. La date est une chaîne de longueur constante littérale du formulaire *Mmm jj aaaa*. Le nom du mois *Mmm* est le même que le nom de mois abrégé dans dates générées par la bibliothèque Runtime C [asctime](../c-runtime-library/reference/asctime-wasctime.md) (fonction). Le premier caractère de date *jj* est un espace si la valeur est inférieure à 10. Cette macro est toujours définie.  
  
-   **__FILE\_\_** le nom du fichier source actuel. **__FILE\_\_** se développe en une chaîne de caractères littérale. Pour vous assurer que le chemin d’accès complet au fichier s’affiche, utilisez [/FC (Full chemin d’accès du fichier de Code Source dans les Diagnostics)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md). Cette macro est toujours définie.  
  
-   **__LINE\_\_** défini comme le numéro de ligne entière dans le fichier source actuel. La valeur de la **__LINE\_\_** macro peut être modifiée en utilisant un `#line` directive. Cette macro est toujours définie.  
  
-   **__STDC\_\_** défini à 1 uniquement lorsque compilé en C et si le [/Za](../build/reference/za-ze-disable-language-extensions.md) option du compilateur est spécifiée. Sinon, non défini.  
  
-   **__STDC_HOSTED\_\_** défini à 1 si l’implémentation est un *hébergé implémentation*, qui prend en charge l’intégralité de la bibliothèque standard requis. Dans le cas contraire, elle est définie comme 0.  
  
-   **__STDCPP_THREADS\_\_** défini à 1 si et seulement si un programme peut avoir plusieurs threads d’exécution et compilé en tant que C++. Sinon, non défini.  
  
-   **__TIME\_\_** l’heure de la traduction de l’unité de traduction prétraité. Le temps est une chaîne de caractères littérale du formulaire *hh : mm :*, identique à l’heure retournée par la bibliothèque Runtime C [asctime](../c-runtime-library/reference/asctime-wasctime.md) (fonction). Cette macro est toujours définie.  
  
## <a name="microsoft-specific-predefined-macros"></a>Macros prédéfinies spécifiques à Microsoft  
 Microsoft Visual C++ prend en charge ces macros prédéfinies supplémentaires.  
  
-   **__ATOM\_\_** défini comme 1 lorsque la [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md) option du compilateur est définie et la cible du compilateur est x86 ou x64. Sinon, non défini.  
  
-   **__AVX\_\_** défini comme 1 lorsque la [AVX](../build/reference/arch-x86.md) ou [/arch : avx2](../build/reference/arch-x86.md) options du compilateur sont définies et la cible du compilateur est x86 ou x64. Sinon, non défini.  
  
-   **__AVX2\_\_** défini comme 1 lorsque la [/arch : avx2](../build/reference/arch-x86.md) option du compilateur est définie et la cible du compilateur est x86 ou x64. Sinon, non défini.  
  
-   **_CHAR_UNSIGNED** définie comme 1, si la valeur par défaut `char` type n’est pas signé. Cette option est définie lorsque le [/J (caractère par défaut est de Type non signé)](../build/reference/j-default-char-type-is-unsigned.md) option du compilateur est définie. Sinon, non défini.  
  
-   **__CLR_VER** définie comme un littéral d’entier qui représente la version du CLR utilisée lors de l’application a été compilée. La valeur est encodée sous la forme `Mmmbbbbb`, où `M` est la version principale du runtime, `mm` est la version secondaire du runtime, et `bbbbb` est le numéro de build. **__CLR_VER** est définie si le [/clr](../build/reference/clr-common-language-runtime-compilation.md) option du compilateur est définie. Sinon, non défini.  
  
    ```cpp  
    // clr_ver.cpp  
    // compile with: /clr  
    using namespace System;  
    int main() {  
       Console::WriteLine(__CLR_VER);  
    }  
    ```  
  
-   **_CONTROL_FLOW_GUARD** défini comme 1 lorsque la [/guard:cf (activer le contrôle de la protection du flux)](../build/reference/guard-enable-control-flow-guard.md) option du compilateur est définie. Sinon, non défini.  
  
-   **__COUNTER\_\_** développe en un littéral d’entier qui commence à 0 et est incrémenté de 1 chaque fois qu’il est utilisé dans un fichier source ou dans les en-têtes du fichier source inclus. **__COUNTER\_\_** conserve son état lorsque vous utilisez des en-têtes précompilés. Cette macro est toujours définie.  
  
     Cet exemple utilise `__COUNTER__` pour assigner des identificateurs uniques à trois objets différents du même type. Le `exampleClass` constructeur accepte un entier comme paramètre. Dans `main`, l’application déclare trois objets de type `exampleClass`, en utilisant `__COUNTER__` comme paramètre d’identificateur unique :  
  
    ```cpp  
    // macro__COUNTER__.cpp  
    // Demonstration of __COUNTER__, assigns unique identifiers to  
    // different objects of the same type.  
    // Compile by using: cl /EHsc /W4 macro__COUNTER__.cpp  
    #include <stdio.h>  
  
    class exampleClass {  
        int m_nID;  
    public:  
        // initialize object with a read-only unique ID  
        exampleClass(int nID) : m_nID(nID) {}  
        int GetID(void) { return m_nID; }  
    };  
  
    int main()  
    {  
        // __COUNTER__ is initially defined as 0  
        exampleClass e1(__COUNTER__);  
  
        // On the second reference, __COUNTER__ is now defined as 1  
        exampleClass e2(__COUNTER__);  
  
        // __COUNTER__ is now defined as 2  
        exampleClass e3(__COUNTER__);  
  
        printf("e1 ID: %i\n", e1.GetID());  
        printf("e2 ID: %i\n", e2.GetID());  
        printf("e3 ID: %i\n", e3.GetID());  
  
        // Output  
        // ------------------------------  
        // e1 ID: 0  
        // e2 ID: 1  
        // e3 ID: 2  
  
        return 0;  
    }  
    ```  
  
-   **__cplusplus_cli** définie comme la valeur de littéral d’entier 200406 lors de la compilation c++ et [/clr](../build/reference/clr-common-language-runtime-compilation.md), [/clr : pure](../build/reference/clr-common-language-runtime-compilation.md), ou [/clr : safe](../build/reference/clr-common-language-runtime-compilation.md) option du compilateur est définie. Sinon, non défini. Lorsque défini, **__cplusplus_cli** est appliqué dans l’unité de traduction.  
  
    ```cpp  
    // cplusplus_cli.cpp  
    // compile by using /clr  
    #include "stdio.h"  
    int main() {  
       #ifdef __cplusplus_cli  
          printf("%d\n", __cplusplus_cli);  
       #else  
          printf("not defined\n");  
       #endif  
    }  
    ```  
  
-   **__cplusplus_winrt** définie comme la valeur de littéral d’entier 201009 lors de la compilation c++ et [/ZW (Compilation Windows Runtime)](../build/reference/zw-windows-runtime-compilation.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_CPPRTTI** définie comme 1, si le [/GR (activer les informations de Type au moment de l’exécution)](../build/reference/gr-enable-run-time-type-information.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_CPPUNWIND** défini à 1 si une ou plusieurs de la [/GX (activer la gestion des exceptions)](../build/reference/gx-enable-exception-handling.md), [/clr (Compilation pour le Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md), ou [/EH (Exception Handling Model)](../build/reference/eh-exception-handling-model.md) options du compilateur sont définies. Sinon, non défini.  
  
-   **_DEBUG** défini comme 1 lorsque la [/LDd](../build/reference/md-mt-ld-use-run-time-library.md), [/MDd](../build/reference/md-mt-ld-use-run-time-library.md), ou [/MTd](../build/reference/md-mt-ld-use-run-time-library.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_DLL** défini comme 1 lorsque la [/MD](../build/reference/md-mt-ld-use-run-time-library.md) ou [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) option de compilateur (DLL multithread) est définie. Sinon, non défini.  
  
-   **__FUNCDNAME\_\_** définie comme un littéral de chaîne qui contient le [nom décoré](../build/reference/decorated-names.md) de la fonction englobante. La macro est définie uniquement dans une fonction. Le **__FUNCDNAME\_\_** macro n’est pas développée si vous utilisez la [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) ou [/P](../build/reference/p-preprocess-to-a-file.md) option du compilateur.  
  
     Cet exemple utilise le `__FUNCDNAME__`, `__FUNCSIG__`, et `__FUNCTION__` macros pour afficher des informations sur la fonction.  
  
     [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]  
  
-   **__FUNCSIG\_\_** définie comme un littéral de chaîne qui contient la signature de la fonction englobante. La macro est définie uniquement dans une fonction. Le **__FUNCSIG\_\_** macro n’est pas développée si vous utilisez la [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) ou [/P](../build/reference/p-preprocess-to-a-file.md) option du compilateur. Lors de la compilation d’une cible de 64 bits, la convention d’appel est `__cdecl` par défaut. Pour obtenir un exemple d’utilisation, consultez le `__FUNCDNAME__` (macro).  
  
-   **__FUNCTION\_\_** définie comme un littéral de chaîne qui contient le nom non décoré de la fonction englobante. La macro est définie uniquement dans une fonction. Le **__FUNCTION\_\_** macro n’est pas développée si vous utilisez la [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) ou [/P](../build/reference/p-preprocess-to-a-file.md) option du compilateur. Pour obtenir un exemple d’utilisation, consultez le `__FUNCDNAME__` (macro).  
  
-   **_INTEGRAL_MAX_BITS** définis en tant que la valeur de littéral d’entier 64, la taille maximale (en octets) d’un type intégral non vectoriel. Cette macro est toujours définie.  
  
    ```cpp  
    // integral_max_bits.cpp  
    #include <stdio.h>  
    int main() {  
       printf("%d\n", _INTEGRAL_MAX_BITS);  
    }  
    ```  
  
-   **__INTELLISENSE\_\_** définie comme passer de 1 pendant un compilateur d’IntelliSense dans l’IDE de Visual Studio. Sinon, non défini. Vous pouvez utiliser cette macro pour protéger le code, le compilateur IntelliSense ne pas comprendre ou utiliser pour basculer entre la génération et du compilateur IntelliSense. Pour plus d’informations, consultez [conseils de dépannage pour IntelliSense lenteur](https://blogs.msdn.microsoft.com/vcblog/2011/03/29/troubleshooting-tips-for-intellisense-slowness/).  
  
-   **_ISO_VOLATILE** définie comme 1, si le [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_KERNEL_MODE** définie comme 1, si le [/kernel (créer Kernel Mode binaire)](../build/reference/kernel-create-kernel-mode-binary.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_M_AMD64** défini comme le littéral d’entier valeur 100 pour les compilations qui x64 de cibler les processeurs. Sinon, non défini.  
  
-   **_M_ARM** définie comme la valeur de littéral d’entier 7 pour les compilations qui ciblent des processeurs ARM. Sinon, non défini.  
  
-   **_M_ARM_ARMV7VE** défini comme 1 lorsque la [armv7ve](../build/reference/arch-arm.md) option du compilateur est définie pour les compilations qui ciblent des processeurs ARM. Sinon, non défini.  
  
-   **_M_ARM_FP** définie comme une valeur littérale entière qui indique quelle [/arch](../build/reference/arch-arm.md) option du compilateur a été définie, si la cible de compilation est un processeur ARM. Sinon, non défini.  
  
    -   Dans la plage 30-39, si aucun **/arch** ARM a été spécifiée, indiquant l’architecture par défaut pour ARM a été définie (`VFPv3`).  
  
    -   Dans la plage 40-49 si **vfpv4** a été défini.  
  
    -   Consultez [/arch (ARM)](../build/reference/arch-arm.md) Pour plus d’informations.  
  
-   **_M_ARM64** défini à 1 pour les compilations qui ciblent des processeurs ARM de 64 bits. Sinon, non défini.  
  
-   **_M_CEE** défini comme 001 si les [/clr (Compilation pour le Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_M_CEE_PURE** défini comme 001 si le [/clr : pure](../build/reference/clr-common-language-runtime-compilation.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_M_CEE_SAFE** défini comme 001 si le [/clr : safe](../build/reference/clr-common-language-runtime-compilation.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_M_FP_EXCEPT** définie comme 1, si le [/fp : sauf](../build/reference/fp-specify-floating-point-behavior.md) ou [/fp : strict](../build/reference/fp-specify-floating-point-behavior.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_M_FP_FAST** définie comme 1, si le [/fp : Fast](../build/reference/fp-specify-floating-point-behavior.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_M_FP_PRECISE** définie comme 1, si le [/fp : precise](../build/reference/fp-specify-floating-point-behavior.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_M_FP_STRICT** définie comme 1, si le [/fp : strict](../build/reference/fp-specify-floating-point-behavior.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_M_IX86** défini comme le littéral d’entier valeur 600 pour les compilations qui x86 de cibler les processeurs. Cette macro n’est pas définie pour x64 ou des cibles de compilation ARM.  
  
-   **_M_IX86_FP** définie comme une valeur littérale entière indiquant la [/arch](../build/reference/arch-arm.md) option du compilateur qui a été définie, ou la valeur par défaut. Cette macro est toujours définie lorsque la cible de compilation est un x86 processeur. Sinon, non défini. Lorsque défini, la valeur est :  
  
    -   0 si le **/arch:IA32** option du compilateur a été définie.  
  
    -   1 si le **/arch : SSE** option du compilateur a été définie.  
  
    -   2 si le **/arch : SSE2**, **AVX** ou **/arch : avx2** option du compilateur a été définie. Cette valeur est la valeur par défaut si un **/arch** option du compilateur n’a pas été spécifiée. Lorsque **AVX** est spécifié, la macro **__AVX\_\_** est également définie. Lorsque **/arch : avx2** est spécifié, les deux **__AVX\_\_** et **__AVX2\_\_** sont également définies.  
  
    -   Consultez [/arch (x86)](../build/reference/arch-x86.md) Pour plus d’informations.  
  
-   **_M_X64** défini comme le littéral d’entier valeur 100 pour les compilations qui x64 de cibler les processeurs. Sinon, non défini.  
  
-   **_MANAGED** défini comme 1 lorsque la [/clr](../build/reference/clr-common-language-runtime-compilation.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_MSC_BUILD** définie comme un littéral d’entier qui contient l’élément de numéro de révision du numéro de version du compilateur. Le numéro de révision est le quatrième élément du numéro de version délimité. Par exemple, si le numéro de version du compilateur Visual C++ est 15.00.20706.01, la **_MSC_BUILD** macro est égale à 1. Cette macro est toujours définie.  
  
-   **_MSC_EXTENSIONS** définie comme 1, si le [/Ze (activer les Extensions de langage)](../build/reference/za-ze-disable-language-extensions.md) option du compilateur est définie, la valeur par défaut. Sinon, non défini.  
  
-   **_MSC_FULL_VER** définie comme un littéral d’entier qui code les principales, mineure et créer des éléments numéro du numéro de version du compilateur. Le numéro principal est le premier élément du numéro de version délimité, le numéro secondaire est le deuxième élément, et le numéro de build est le troisième élément. Par exemple, si le numéro de version du compilateur Visual C++ est 15.00.20706.01, la **_MSC_FULL_VER** macro prend la valeur 150020706. Entrez **cl / ?** dans la ligne de commande pour afficher le numéro de version du compilateur. Cette macro est toujours définie.  
  
-   **_MSC_VER** définie comme un littéral d’entier qui code les éléments numéro principales et secondaires du numéro de version du compilateur. Le numéro principal est le premier élément du numéro de version délimité et le numéro secondaire est le deuxième élément. Par exemple, si le numéro de version du compilateur Visual C++ est 17.00.51106.1, la **_MSC_VER** macro prend la valeur 1700. Entrez **cl / ?** dans la ligne de commande pour afficher le numéro de version du compilateur. Cette macro est toujours définie.  
  
-   **_MSVC_LANG** définie comme un littéral d’entier qui spécifie la norme du langage C++ ciblée par le compilateur. Lors de la compilation c++, la macro est la valeur de littéral entier 201402 si le [/std:c ++ 14](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) option du compilateur est défini, ou par défaut et elle est définie sur un degré plus élevé, n’est pas spécifié valeur lorsque le [/std:c ++ dernières](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) option du compilateur est définie. Dans le cas contraire, la macro n’est pas définie. Le **_MSVC_LANG** macro et [/std (spécifier la Version Standard traduite)](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) options du compilateur sont disponibles à partir de Visual Studio 2015 Update 3.  
  
-   **__MSVC_RUNTIME_CHECKS** défini à 1 lorsqu’un de le [/RTC](../build/reference/rtc-run-time-error-checks.md) options du compilateur est définie. Sinon, non défini.  
  
-   **_MT** défini comme 1 lorsque [/MD ou /MDd](../build/reference/md-mt-ld-use-run-time-library.md) (DLL multithread) ou [/MT ou /MTd](../build/reference/md-mt-ld-use-run-time-library.md) (multithread) est spécifié. Sinon, non défini.  
  
-   **_NATIVE_WCHAR_T_DEFINED** défini comme 1 lorsque la [/Zc :](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_OPENMP** entier littéral 200203, représentant la date de la spécification OpenMP implémentée par Visual C++, si le [/openmp (activer OpenMP 2.0 prise en charge)](../build/reference/openmp-enable-openmp-2-0-support.md) option du compilateur est définie. Sinon, non défini.  
  
    ```cpp  
    // _OPENMP_dir.cpp  
    // compile with: /openmp   
    #include <stdio.h>   
    int main() {  
       printf("%d\n", _OPENMP);  
    }  
    ```  
  
-   **_PREFAST\_** défini comme 1 lorsque la [/ analyze](../build/reference/analyze-code-analysis.md) option du compilateur est définie. Sinon, non défini.  
  
-   **__TIMESTAMP\_\_** définie comme un littéral de chaîne qui contient la date et l’heure de la dernière modification du fichier source actuel, sous la forme abrégée de longueur constante renvoyée par la bibliothèque Runtime C [asctime](../c-runtime-library/reference/asctime-wasctime.md) de fonction, par exemple, `Fri 19 Aug 13:32:58 2016`. Cette macro est toujours définie.  
  
-   **_VC_NODEFAULTLIB** défini comme 1 lorsque la [/Zl (omettre les nom de bibliothèque par défaut)](../build/reference/zl-omit-default-library-name.md) option du compilateur est définie. Sinon, non défini.  
  
-   **_WCHAR_T_DEFINED** défini comme 1 lorsque la valeur par défaut [/Zc :](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) option du compilateur est définie. Le **_WCHAR_T_DEFINED** macro est définie, mais elle n’a aucune valeur si le **/Zc:wchar_t-** option du compilateur est définie, et `wchar_t` est défini dans un fichier d’en-tête système inclus dans votre projet. Sinon, non défini.  
  
-   **_WIN32** définis comme 1 lorsque la cible de compilation est ARM 32 bits, 64 bits, ARM, x86, ou x 64. Sinon, non défini.  
  
-   **_WIN64** défini à 1 lorsque la cible de compilation est 64 bits ARM ou x64. Sinon, non défini.  
  
-   **_WINRT_DLL** défini en tant que 1 lorsque compilé en tant que C++ ainsi que les [/ZW (Compilation Windows Runtime)](../build/reference/zw-windows-runtime-compilation.md) et [/LD ou /LDd](../build/reference/md-mt-ld-use-run-time-library.md) options du compilateur sont définies. Sinon, non défini.  
  
 Macros de préprocesseur permet de déterminer la version de la bibliothèque ATL ou MFC ne sont pas prédéfinies par le compilateur. Ces macros sont définies dans les en-têtes de la bibliothèque, ils sont non définies dans les directives de préprocesseur avant l’en-tête requis n’est inclus.  
  
-   **_ATL_VER** défini dans \< atldef.h > comme un littéral d’entier qui encode le numéro de version ATL.  
  
-   **_MFC_VER** défini dans \< afxver_.h > comme un littéral d’entier qui encode le numéro de version MFC.  
  
## <a name="see-also"></a>Voir aussi  
 [Macros (C/C++)](../preprocessor/macros-c-cpp.md)   
 [Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md)   
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)