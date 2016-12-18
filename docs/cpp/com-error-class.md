---
title: "_com_error, classe | Microsoft Docs"
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
  - "_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error (classe)"
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Un objet `_com_error` représente une condition d'exception détectée par les fonctions wrapper de gestion des erreurs dans les fichiers d'en\-tête générés par la bibliothèque de types ou une des classes de prise en charge COM.  La classe `_com_error` encapsule le code d'erreur `HRESULT` et tout objet `IErrorInfo Interface` associé.  
  
### Construction  
  
|||  
|-|-|  
|[\_com\_error](../cpp/com-error-com-error.md)|Construit un objet `_com_error`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[\=, opérateur](../cpp/com-error-operator-equal.md)|Assigne un objet `_com_error` existant à un autre.|  
  
### Fonctions d'extracteur  
  
|||  
|-|-|  
|[Erreur](../cpp/com-error-error.md)|Récupère le `HRESULT` passé au constructeur.|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Récupère l'objet `IErrorInfo` passé au constructeur.|  
|[WCode](../cpp/com-error-wcode.md)|Récupère le code d'erreur 16 bits mappé au `HRESULT`encapsulée.|  
  
### Fonctions d'IErrorInfo  
  
|||  
|-|-|  
|[Description](../cpp/com-error-description.md)|Appels la fonction `IErrorInfo::GetDescription`|  
|[Helpcontext](../cpp/com-error-helpcontext.md)|Appels la fonction `IErrorInfo::GetHelpContext`.|  
|[Helpfile](../cpp/com-error-helpfile.md)|Appels la fonction `IErrorInfo::GetHelpFile`.|  
|[Source](../cpp/com-error-source.md)|Appels la fonction `IErrorInfo::GetSource`.|  
|[GUID](../cpp/com-error-guid.md)|Appels la fonction `IErrorInfo::GetGUID`.|  
  
### Extracteur de message de format  
  
|||  
|-|-|  
|[ErrorMessage](../cpp/com-error-errormessage.md)|Récupère le message de chaîne pour le HRESULT stocké dans l'objet `_com_error`.|  
  
### ExepInfo.wCode aux mappeurs HRESULT  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|Mappe un `HRESULT` 32 bits à un `wCode`16 bits.|  
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|Mappe un `wCode` 16 bits à un `HRESULT`32 bits.|  
  
## END Spécifique à Microsoft  
  
## Configuration requise  
 `Header:` comdef.h  
  
 `Lib:` comsuppw.lib ou comsuppwd.lib \(consultez [\/Zc:wchar\_t \(wchar\_t est un type natif\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) pour plusd'information\)  
  
## Voir aussi  
 [Classes du support COM du compilateur](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo Interface](http://msdn.microsoft.com/fr-fr/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)