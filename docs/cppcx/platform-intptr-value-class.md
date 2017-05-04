---
title: "Classe de valeur Platform::IntPtr | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IntPtr (structure)"
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Classe de valeur Platform::IntPtr
Représente un pointeur ou un handle signé dont la taille est propre à la plateforme \(32 bits ou 64 bits\).  
  
## Syntaxe  
  
```cpp  
public value struct IntPtr  
```  
  
## Membres  
 IntPtr a les membres suivants :  
  
|Membre|Description|  
|------------|-----------------|  
|[IntPtr::IntPtr \(constructeur\)](../cppcx/intptr-intptr-constructor.md)|Initialise une nouvelle instance d'IntPtr.|  
|[IntPtr::op\_explicit, opérateur](../cppcx/intptr-op-explicit-operator.md)|Convertit le paramètre spécifié en un IntPtr ou un pointeur en une valeur IntPtr.|  
|[IntPtr::ToInt32 \(méthode\)](../cppcx/intptr-toint32-method.md)|Convertit l'IntPtr actif en un entier 32 bits.|  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)