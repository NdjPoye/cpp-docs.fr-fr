---
title: "_initterm, _initterm_e | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_initterm_e"
  - "_initterm"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_initterm_e"
  - "initterm"
  - "_initterm"
  - "initterm_e"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "initterm (fonction)"
  - "initterm_e (fonction)"
  - "_initterm (fonction)"
  - "_initterm_e (fonction)"
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _initterm, _initterm_e
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Méthodes internes qui parcourent une table de pointeurs de fonction et les initialisent.  
  
 Le premier pointeur est l'emplacement de début dans la table et le second pointeur est l'emplacement de fin.  
  
## Syntaxe  
  
```  
void __cdecl _initterm(  
   PVFV *,  
   PVFV *  
);  
  
int __cdecl _initterm_e(  
   PVFV *,  
   PVFV *  
);  
```  
  
## Valeur de retour  
 Un code d'erreur différent de zéro si l'initialisation échoue et génère une erreur ; 0 si aucune erreur ne se produit.  
  
## Notes  
 Ces méthodes sont appelées uniquement en interne pendant l'initialisation du programme C\+\+.  N'appelez pas ces méthodes dans un programme.  
  
 Lorsque ces méthodes parcourent un tableau d'entrées de fonction, elles ignorent les entrées `NULL` et continuent.  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)