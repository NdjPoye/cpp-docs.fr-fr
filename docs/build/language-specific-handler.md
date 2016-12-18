---
title: "Gestionnaire sp&#233;cifique au langage | Microsoft Docs"
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
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Gestionnaire sp&#233;cifique au langage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'adresse relative du gestionnaire spécifique au langage est présente dans UNWIND\_INFO chaque fois que les indicateurs UNW\_FLAG\_EHANDLER ou UNW\_FLAG\_UHANDLER sont définis.  Comme décrit dans la section précédente, le gestionnaire spécifique au langage est appelé dans le cadre de la recherche d'un gestionnaire d'exceptions ou dans le cadre d'un déroulement.  Il comporte le prototype suivant :  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** fournit un pointeur vers un enregistrement d'exception possédant la définition Win64 standard.  
  
 **EstablisherFrame** est l'adresse de la base de la pile d'allocation fixe pour cette fonction.  
  
 **ContextRecord** pointe vers le contexte d'exception au moment de la levée de l'exception \(dans le cas du gestionnaire d'exceptions\) ou dans le contexte de « déroulement » actuel \(dans le cas du gestionnaire de terminaisons\).  
  
 **DispatcherContext** pointe vers le contexte de répartiteur de cette fonction.  Il comporte la définition suivante :  
  
```  
typedef struct _DISPATCHER_CONTEXT {  
    ULONG64 ControlPc;  
    ULONG64 ImageBase;  
    PRUNTIME_FUNCTION FunctionEntry;  
    ULONG64 EstablisherFrame;  
    ULONG64 TargetIp;  
    PCONTEXT ContextRecord;  
    PEXCEPTION_ROUTINE LanguageHandler;  
    PVOID HandlerData;  
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;  
```  
  
 **ControlPc** est la valeur de RIP dans cette fonction.  Il s'agit d'une adresse d'exception ou de l'adresse à laquelle le contrôle a quitté la fonction de mise en place.  Ce RIP sera utilisé pour déterminer si le contrôle se trouve dans une construction protégée au sein de cette fonction \(par exemple, un bloc \_\_try pour \_\_try\/\_\_except ou \_\_try\/\_\_finally\).  
  
 **ImageBase** est la base d'image \(adresse de chargement\) du module qui contient cette fonction, à ajouter aux offsets de 32 bits utilisés dans l'entrée de fonction et dans les informations de déroulement pour enregistrer des adresses relatives.  
  
 **FunctionEntry** fournit un pointeur vers l'entrée de fonction RUNTIME\_FUNCTION contenant les adresses relatives de la base d'image de la fonction et des informations de déroulement pour cette fonction.  
  
 **EstablisherFrame** est l'adresse de la base de la pile d'allocation fixe pour cette fonction.  
  
 **TargetIp** fournit une adresse d'instruction facultative spécifiant l'adresse de continuation du déroulement.  Cette adresse est ignorée si **EstablisherFrame** n'est pas spécifié.  
  
 **ContextRecord** pointe vers le contexte d'exception que le code de répartition\/déroulement des exceptions du système doit utiliser.  
  
 **LanguageHandler** pointe vers la routine du gestionnaire spécifique au langage appelé.  
  
 **HandlerData** pointe vers les données du gestionnaire spécifique au langage pour cette fonction.  
  
## Voir aussi  
 [Gestion des exceptions \(x64\)](../build/exception-handling-x64.md)