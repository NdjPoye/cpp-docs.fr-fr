---
title: "/SAFESEH (L&#39;image est dot&#233;e de gestionnaires d&#39;exceptions s&#233;curis&#233;s) | Microsoft Docs"
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
  - "/SAFESEH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SAFESEH (option de l'éditeur de liens)"
  - "-SAFESEH (option de l'éditeur de liens)"
  - "SAFESEH (option de l'éditeur de liens)"
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SAFESEH (L&#39;image est dot&#233;e de gestionnaires d&#39;exceptions s&#233;curis&#233;s)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SAFESEH[:NO]  
```  
  
 Lorsque **\/SAFESEH** est spécifié, l'éditeur de liens produit uniquement une image s'il peut également produire une table des gestionnaires d'exceptions sécurisés de l'image.  Cette table indique au système d'exploitation les gestionnaires d'exceptions valides pour l'image.  
  
 **\/SAFESEH** n'est valide que lors de la liaison de cibles x86.  L'option **\/SAFESEH** n'est pas prise en charge pour les plates\-formes dont les gestionnaires d'exceptions sont déjà définis.  Par exemple, sur [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] et ARM, tous les gestionnaires d'exceptions sont indiqués dans le PDATA.  ML64.exe prend en charge l'ajoute d'annotations qui émettent des informations SEH \(XDATA et PDATA\) dans l'image, ce qui vous permet de procéder au déroulement à l'aide de fonctions ml64.  Pour plus d'informations, consultez [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
 Si **\/SAFESEH** n'est pas spécifié, l'éditeur de liens produit une image avec une table des gestionnaires d'exceptions sécurisés si tous les modules sont compatibles avec la fonction de gestion sécurisée des exceptions.  Si des modules n'étaient pas compatibles avec la fonction de gestion sécurisée des exceptions, l'image résultante ne contient pas de table des gestionnaires d'exceptions sécurisés.  Si [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) spécifie WINDOWSCE ou l'une des options EFI\_\*, l'éditeur de liens ne tente pas de produire une image avec une table des gestionnaires d'exceptions sécurisés, puisque aucun de ces sous\-systèmes n'est en mesure d'utiliser les informations.  
  
 Si **\/SAFESEH:NO** est spécifié, l'éditeur de liens ne produit d'image avec une table des gestionnaires d'exceptions sécurisés, même si tous les modules sont compatibles avec la fonction de gestion sécurisée des exceptions.  
  
 La cause la plus fréquente de l'impossibilité pour l'éditeur de liens de produire une image est l'incompatibilité d'un ou de plusieurs des fichiers d'entrée \(modules\) à l'éditeur de liens avec la fonction de gestion sécurisée des exceptions.  La non\-compatibilité d'un module avec des gestionnaires d'exceptions sécurisés est souvent due à sa création par un compilateur d'une version précédente de Visual C\+\+.  
  
 Vous pouvez également enregistrer une fonction en tant que gestionnaire d'exceptions structuré à l'aide de [.SAFESEH](../../assembler/masm/dot-safeseh.md).  
  
 Dans , il n'est pas possible de marquer un fichier binaire existant comme ayant des gestionnaires d'exceptions sécurisés \(ou aucun gestionnaire d'exceptions\) ; les informations sur la gestion sécurisée des exceptions doivent être ajoutées au moment de la génération.  
  
 L'éditeur de liens ne peut générer une table des gestionnaires d'exceptions sécurisés que si l'application utilise la bibliothèque Microsoft C Runtime.  Si vous créez un lien avec [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) et souhaitez obtenir une table des gestionnaires d'exceptions sécurisés, vous devez fournir une structure de configuration de charge \(comme celle du fichier source CRT loadcfg.c\) qui contient toutes les entrées définies pour Visual C\+\+.  Par exemple :  
  
```  
#include <windows.h>  
extern DWORD_PTR __security_cookie;  /* /GS security cookie */  
  
/*  
 * The following two names are automatically created by the linker for any  
 * image that has the safe exception table present.  
*/  
  
extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */  
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is  
                                           the count of table entries */  
typedef struct {  
    DWORD       Size;  
    DWORD       TimeDateStamp;  
    WORD        MajorVersion;  
    WORD        MinorVersion;  
    DWORD       GlobalFlagsClear;  
    DWORD       GlobalFlagsSet;  
    DWORD       CriticalSectionDefaultTimeout;  
    DWORD       DeCommitFreeBlockThreshold;  
    DWORD       DeCommitTotalFreeThreshold;  
    DWORD       LockPrefixTable;            // VA  
    DWORD       MaximumAllocationSize;  
    DWORD       VirtualMemoryThreshold;  
    DWORD       ProcessHeapFlags;  
    DWORD       ProcessAffinityMask;  
    WORD        CSDVersion;  
    WORD        Reserved1;  
    DWORD       EditList;                   // VA  
    DWORD_PTR   *SecurityCookie;  
    PVOID       *SEHandlerTable;  
    DWORD       SEHandlerCount;  
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;  
  
const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {  
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    &__security_cookie,  
    __safe_se_handler_table,  
    (DWORD)(DWORD_PTR) &__safe_se_handler_count  
};  
```  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Entrez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)