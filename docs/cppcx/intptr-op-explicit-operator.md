---
title: "IntPtr::op_explicit, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr::op_explicit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntPtr::op_explicit (méthode)"
ms.assetid: cc52e9d5-fe73-471b-8cff-d9f684ba6e20
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# IntPtr::op_explicit, op&#233;rateur
Convertit le paramètre spécifié en un IntPtr ou un pointeur en une valeur IntPtr.  
  
## Syntaxe  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
#### Paramètres  
 value1  
 Pointeur vers un handle ou un IntPtr.  
  
 value2  
 Entier 32 bits qui peut être converti en IntPtr.  
  
 valeur3  
 Un IntPtr.  
  
## Valeur de retour  
 Le premier et le deuxième opérateur retournent un IntPtr. Le troisième opérateur retourne un pointeur vers la valeur représentée par l'IntPtr actuel.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Classe de valeur Platform::IntPtr](../cppcx/platform-intptr-value-class.md)