---
title: "IntPtr::IntPtr (constructeur) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr::IntPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntPtr::IntPtr (constructeur)"
ms.assetid: 828b4c18-790d-4fb4-90fe-47769ff381c0
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# IntPtr::IntPtr (constructeur)
Initialise une nouvelle instance d'IntPtr avec la valeur spécifiée.  
  
## Syntaxe  
  
```cpp  
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );  
```  
  
#### Paramètres  
 par défaut  
 Handle ou pointeur 64 bits ou pointeur vers une valeur 64 bits, ou valeur 32 bits qui peut être convertie en valeur 64 bits.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Classe de valeur Platform::IntPtr](../cppcx/platform-intptr-value-class.md)