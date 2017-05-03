---
title: "Platform::Delegate (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Delegate (classe)"
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::Delegate (classe)
Représente un objet de fonction.  
  
## Syntaxe  
  
```cpp  
public delegate void delegate_name();  
```  
  
## Membres  
 La classe Delegate contient les méthodes Equals\(\), GetHashCode\(\), et ToString\(\) dérivées de la [Platform::Object, classe](../cppcx/platform-object-class.md).  
  
## Notes  
 Utilisez le mot clé [delegate](../Topic/delegate%20%20\(C++%20Component%20Extensions\).md) pour créer des délégués. N’utilisez pas Platform::Delegate explicitement. Pour plus d'informations, consultez [Délégués](../cppcx/delegates-c-cx.md). Pour obtenir un exemple montrant comment créer et consommer un délégué, consultez [Création de composants Windows Runtime en C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md).  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)