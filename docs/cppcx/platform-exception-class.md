---
title: "Platform::Exception (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Exception (classe)"
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Exception (classe)
Représente les erreurs qui se produisent lors de l'exécution de l'application. Les classes d'exception personnalisées ne peuvent pas être dérivées d'`Platform::Exception`. Si vous avez besoin d'une exception personnalisée, vous pouvez utiliser `Platform::COMException` et spécifier un HRESULT propre à l'application.  
  
## Syntaxe  
  
```cpp  
public ref class Exception : Object,    IException,    IPrintable,    IEquatable  
```  
  
## Membres  
 La classe `Exception` hérite de la classe `Object` et des interfaces `IException`, `IPrintable` et `IEquatable`.  
  
 La classe `Exception` comporte également les types de membres ci\-dessous.  
  
### Constructeurs  
  
|Membre|Description|  
|------------|-----------------|  
|[Exception::Exception Constructor](../cppcx/exception-exception-constructor.md)|Initialise une nouvelle instance de la classe `Exception`.|  
  
### Méthodes  
 La classe `Exception` hérite des méthodes `Equals()`, `Finalize()`,`GetHashCode()`,`GetType()`,`MemberwiseClose()` et `ToString()` de la [Platform::Object, classe](../cppcx/platform-object-class.md). La classe `Exception` comporte aussi la méthode ci\-dessous.  
  
|Membre|Description|  
|------------|-----------------|  
|[Exception::CreateException \(méthode\)](../cppcx/exception-createexception-method.md)|Crée une exception qui représente la valeur HRESULT spécifiée.|  
  
### Propriétés  
 La classe Exception comporte aussi les propriétés ci\-dessous.  
  
|Membre|Description|  
|------------|-----------------|  
|[Exception::HResult \(propriété\)](../cppcx/exception-hresult-property.md)|HRESULT qui correspond à l'exception.|  
|[Exception::Message \(propriété\)](../cppcx/exception-message-property.md)|Message qui décrit l'exception. Cette valeur est en lecture seule et ne peut pas être modifiée après la construction d'`Exception`.|  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)