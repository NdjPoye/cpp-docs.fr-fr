---
title: "String::operator&gt;+, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator+"
dev_langs: 
  - "C++"
ms.assetid: 919b5ba4-3d3b-47a4-9893-9a9ce51fb9c8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator&gt;+, op&#233;rateur
Indique si deux objets [String](../cppcx/platform-string-class.md) spécifiés ont la même valeur.  
  
## Syntaxe  
  
```cpp  
  
bool String::operator+( String^ str1,  
                         String^ str2)  
  
```  
  
#### Paramètres  
 `str1`  
 Premier objet `String`.  
  
 `str2`  
 Deuxième objet `String` dont le contenu sera ajouté à `str1`.  
  
## Valeur de retour  
 `true` si `str1` est égal à `str2` ; sinon `false`.  
  
## Notes  
 Cet opérateur crée un objet `String^` qui contient les données des deux opérandes. Utilisez\-le pour des raisons pratiques lorsque la performance extrême n'est pas critique. Certains appels à « `+` » dans une fonction ne seront peut\-être pas visibles, mais si vous manipulez des objets volumineux ou des données texte dans une boucle serrée, utilisez ensuite les mécanismes et les types C\+\+ standard.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** vccorlib.h  
  
## Voir aussi  
 [Platform::String, classe](../cppcx/platform-string-class.md)