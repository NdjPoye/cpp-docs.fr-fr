---
title: "Guid::Guid, constructeurs | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Plateforme, Guid::Guid"
  - "Guid::Guid"
ms.assetid: dfa4dcad-1c3b-481f-9f60-05141b9788d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Guid::Guid, constructeurs
Initialise une nouvelle instance d'une structure de Guid.  
  
## Syntaxe  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  
);  
  
    Guid(   
        GUID m  
);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n  
);  
```  
  
#### Paramètres  
 `a`  
 Quatre premiers octets du GUID.  
  
 `b`  
 Deux octets suivants du GUID.  
  
 `c`  
 Deux octets suivants du GUID.  
  
 `d`  
 Octet suivant du GUID.  
  
 `e`  
 Octet suivant du GUID.  
  
 `f`  
 Octet suivant du GUID.  
  
 `g`  
 Octet suivant du GUID.  
  
 `h`  
 Octet suivant du GUID.  
  
 `i`  
 Octet suivant du GUID.  
  
 `j`  
 Octet suivant du GUID.  
  
 `k`  
 Octet suivant du GUID.  
  
 `m`  
 GUID défini.  
  
 `n`  
 Huit octets restants du GUID.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Classe de valeur Platform::Guid](../cppcx/platform-guid-value-class.md)