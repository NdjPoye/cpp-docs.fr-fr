---
title: "Exception::CreateException (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::CreateException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::CreateException (méthode)"
ms.assetid: 70e72bb4-3fec-478d-af3d-9ec8762d2825
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::CreateException (m&#233;thode)
Crée Platform::Exception^ à partir d'une valeur HRESULT spécifique.  
  
## Syntaxe  
  
```cpp  
Exception^ CreateException(int32 hr)  
Exception^ CreateException(int32 hr, Platform::String^ message)  
```  
  
## Paramètres  
 hr  
 Valeur HRESULT que vous obtenez généralement à partir d'un appel à une méthode COM. Si la valeur est 0, c'est\-à\-dire qu'elle est égale à S\_OK, cette méthode lève [Platform::InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md), car les méthodes COM qui réussissent ne doivent pas lever d'exceptions.  
  
 message  
 Chaîne qui décrit l'erreur.  
  
## Valeur de retour  
 Exception qui représente l'erreur HRESULT.  
  
## Notes  
 Utilisez cette méthode pour créer une exception à partir d'une valeur HRESULT retournée, par exemple, à partir d'un appel à une méthode d'interface COM. Utilisez la surcharge qui accepte un paramètre String^ pour fournir un message personnalisé.  
  
 Il est fortement recommandé d'utiliser CreateException pour créer une exception fortement typée au lieu de créer [Platform::COMException](../cppcx/platform-comexception-class.md), qui contient uniquement HRESULT.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)