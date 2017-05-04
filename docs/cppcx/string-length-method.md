---
title: "String::Length, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Length"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Length"
ms.assetid: 92376897-1bf2-4b7a-9298-d2d3f05d8d6b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Length, m&#233;thode
Récupère le nombre de caractères de l'objet String actif.  
  
## Syntaxe  
  
```cpp  
  
unsigned int Length()  
```  
  
## Valeur de retour  
 Nombre de caractères de l'objet String actif.  
  
## Notes  
 La longueur d'une chaîne sans caractères est zéro. La longueur de la chaîne suivante est 5 :  
  
```  
  
String^ str = "Hello";  
int len = str->Length(); //len = 5  
```  
  
 Le tableau de caractères retourné par [String::Data, méthode](../cppcx/string-data-method.md) a un caractère supplémentaire, qui est le caractère de fin NULL ou « \\0 ». La longueur de ce caractère est également de deux octets.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** vccorlib.h  
  
## Voir aussi  
 [Platform::String, classe](../cppcx/platform-string-class.md)