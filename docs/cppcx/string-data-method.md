---
title: "String::Data, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Data"
ms.assetid: 9be4e015-dfb8-431e-a252-8498bd833f03
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Data, m&#233;thode
Retourne un pointeur vers le début de la mémoire tampon de données de l'objet en tant que tableau de style C d'éléments `char16` \(`wchar_t`\).  
  
## Syntaxe  
  
```  
const char16* Data()  
```  
  
## Valeur de retour  
 Pointeur vers le début d’un tableau `const``char16` de caractères Unicode \(`char16` est un typedef pour `wchar_t`\).  
  
## Notes  
 Utilisez cette méthode pour convertir de `Platform::String^` en `wchar_t*`. Lorsque l'objet `String` se trouve hors de portée, la validité du pointeur donnée n'est plus garantie. Pour stocker les données au\-delà de la durée de vie de l'objet `String` d'origine, utilisez [wcscpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) pour copier le tableau dans la mémoire que vous avez allouée à vous\-même.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** vccorlib.h  
  
## Voir aussi  
 [Platform::String, classe](../cppcx/platform-string-class.md)   
 [String::Begin, méthode](../cppcx/string-begin-method.md)