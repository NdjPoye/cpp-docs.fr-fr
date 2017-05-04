---
title: "StringReference::StringReference, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 87dd9201-e638-4913-b37c-7091ae3f91ea
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::StringReference, constructeur
Initialise une nouvelle instance de la classe `StringReference`.  
  
## Syntaxe  
  
```cpp  
  
    StringReference();  
  
   StringReference(const StringReference& __fstrArg)  
  
StringReference(const ::default::char16* __strArg)  
  
StringReference(const ::default::char16* __strArg, size_t __lenArg)  
```  
  
#### Paramètres  
 `__fstrArg`  
 `StringReference` dont les données sont utilisées pour initialiser la nouvelle instance.  
  
 `__strArg`  
 Pointeur vers un tableau de valeurs char16 utilisé pour initialiser la nouvelle instance.  
  
 `__lenArg`  
 Nombre d'éléments de `__strArg`.  
  
## Notes  
 La première version de ce constructeur est le constructeur par défaut. La deuxième version initialise une nouvelle classe d'instance `StringReference` de l'objet spécifié par le paramètre `__fstrArg`. Les troisième et quatrième surcharges initialisent une nouvelle instance de `StringReference` à partir d’un tableau de valeurs char16. char16 représente un caractère de texte UNICODE 16 bits.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::StringReference, classe](../cppcx/platform-stringreference-class.md)