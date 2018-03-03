---
title: "Gestionnaire spécifique au langage | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc15e730666a643dfaa028fe7bc6166144897308
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="language-specific-handler"></a>Gestionnaire spécifique au langage
L’adresse relative du gestionnaire spécifique au langage est présente dans UNWIND_INFO chaque fois que les indicateurs UNW_FLAG_EHANDLER ou UNW_FLAG_UHANDLER sont définis. Comme décrit dans la section précédente, le gestionnaire spécifique au langage est appelé dans le cadre de la recherche d’un gestionnaire d’exceptions ou dans le cadre d’un déroulement. Il a le prototype suivant :  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** fournit un pointeur vers un enregistrement d’exception possédant la définition Win64 standard.  
  
 **EstablisherFrame** est l’adresse de la base de l’allocation de pile fixe pour cette fonction.  
  
 **ContextRecord** contexte (dans le cas du Gestionnaire de terminaisons) pointe vers le contexte d’exception au moment de l’exception a été levée (dans le cas de gestionnaire d’exceptions) ou actuel « déroule ».  
  
 **DispatcherContext** pointe vers le contexte de répartiteur de cette fonction. Il a la définition suivante :  
  
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
  
 **ControlPc** est la valeur de RIP dans cette fonction. Il s’agit d’une adresse de l’exception ou l’adresse à laquelle contrôle gauche de la fonction de mise en place. C’est le protocole RIP qui permet de déterminer si le contrôle est dans une construction protégée au sein de cette fonction (par exemple, un bloc __try pour \__try /\__except ou \__try /\__finally).  
  
 **ImageBase** est l’image de base (adresse de chargement) du module contenant cette fonction, à ajouter aux offsets de 32 bits utilisés dans l’entrée de fonction et informations de déroulement pour enregistrer des adresses relatives.  
  
 **FunctionEntry** fournit un pointeur vers le RUNTIME_FUNCTION entrée de la fonction de la fonction info base d’image adresses relatives et déroulement de cette fonction.  
  
 **EstablisherFrame** est l’adresse de la base de l’allocation de pile fixe pour cette fonction.  
  
 **TargetIp** fournit une adresse d’instruction facultatif qui spécifie l’adresse de la continuation du déroulement. Cette adresse est ignorée si **EstablisherFrame** n’est pas spécifié.  
  
 **ContextRecord** pointe vers le contexte d’exception, pour une utilisation par le code de répartition/déroulement d’exception système.  
  
 **LanguageHandler** pointe vers la routine du gestionnaire spécifique au langage appelé.  
  
 **HandlerData** pointe vers les données du gestionnaire spécifique au langage pour cette fonction.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des exceptions (x64)](../build/exception-handling-x64.md)