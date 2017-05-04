---
title: "Platform::COMException (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::COMException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::COMException (classe)"
ms.assetid: 44fda4e5-574f-4d12-ab5f-4ff3f277448d
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::COMException (classe)
Représente les erreurs COM qui se produisent lors de l'exécution de l'application. COMException est la classe de base pour un jeu d'exceptions prédéfinies et standard.  
  
## Syntaxe  
  
```cpp  
public ref class COMException : Exception,    IException,    IPrintable,    IEquatable  
```  
  
## Membres  
 La classe COMException hérite de la classe d'objets et des interfaces IException, IPrintable et IEquatable.  
  
 COMException a également les types de membre suivants.  
  
 **Constructeurs**  
  
|Membre|Description|  
|------------|-----------------|  
|`COMException`|Initialise une nouvelle instance de la classe COMException.|  
  
 **Méthodes**  
  
 La classe COMException hérite des méthodes Equals\(\), Finalize\(\), GetHashCode\(\), GetType\(\), MemberwiseClose\(\) et ToString\(\) de [Platform::Object, classe](../cppcx/platform-object-class.md).  
  
 **Propriétés**  
  
 La classe COMException a les propriétés ci\-dessous.  
  
|Membre|Description|  
|------------|-----------------|  
|[Exception::HResult \(propriété\)](../cppcx/exception-hresult-property.md)|HRESULT qui correspond à l'exception.|  
|[Exception::Message \(propriété\)](../cppcx/exception-message-property.md)|Message décrivant l'exception.|  
  
## Exceptions dérivées  
 Les exceptions prédéfinies suivantes sont dérivées de COMException. Elles diffèrent de COMException uniquement au niveau de leur nom, du nom de leur constructeur et de leur valeur HRESULT sous\-jacente.  
  
|Nom|HRESULT sous\-jacent|Description|  
|---------|--------------------------|-----------------|  
|COMException|*hresult défini par l’utilisateur*|Levée lorsqu'un HRESULT non reconnu est retourné d'un appel de méthode COM.|  
|AccessDeniedException|E\_ACCESSDENIED|Levée lorsque l'accès est refusé à une ressource ou à une fonctionnalité.|  
|ChangedStateException|E\_CHANGED\_STATE|Levée lorsque les méthodes d'un itérateur de collection ou d'une vue de collection sont appelées après la modification d'une collection parente, invalidant les résultats de la méthode.|  
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|Levée lorsqu'une classe COM n'a pas été inscrite.|  
|DisconnectedException|RPC\_E\_DISCONNECTED|Levée lorsqu'un objet est déconnecté de ses clients.|  
|FailureException|E\_FAIL|Levée lorsqu'une opération échoue.|  
|InvalidArgumentException|E\_INVALIDARG|Levée lorsque l'un des arguments fournis à une méthode n'est pas valide.|  
|InvalidCastException|E\_NOINTERFACE|Levée lorsqu'un type ne peut pas être casté en un autre type.|  
|NotImplementedException|E\_NOTIMPL|Levée si une méthode d'interface n'a pas été implémentée pour une classe.|  
|NullReferenceException|E\_POINTER|Levée lors d'une tentative de suppression de la référence à une référence d'objet null.|  
|OperationCanceledException|E\_ABORT|Levée lorsqu'une opération est abandonnée.|  
|OutOfBoundsException|E\_BOUNDS|Levée lorsqu'une opération tente d'accéder aux données en dehors de la plage valide.|  
|OutOfMemoryException|E\_OUTOFMEMORY|Levée en cas de mémoire insuffisante pour terminer l'opération.|  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)