---
title: "&lt;string&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<string>"
  - "string/std::<string>"
  - "std.<string>"
  - "<string>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête de chaîne"
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
caps.latest.revision: 23
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;string&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit la classe de modèle de conteneur `basic_string` et divers modèles de prise en charge.  
  
 Pour plus d'informations sur `basic_string`, consultez [basic\_string, classe](../standard-library/basic-string-class.md).  
  
## Syntaxe  
  
```  
#include <string>  
```  
  
## Notes  
 Le langage C\+\+ et la bibliothèque C\+\+ standard prennent en charge deux types de chaîne :  
  
-   tableaux de caractères se terminant par un caractère Null et souvent appelés chaînes C ;  
  
-   objets de classe de modèle, de type `basic_string`, qui gèrent tous les arguments de modèle de type `char`.  
  
### Typedef  
  
|||  
|-|-|  
|[string](../Topic/string%20\(C++%20STL%20%3Cstring%3E\).md)|Type qui décrit une spécialisation de la classe de modèle `basic_string` avec des éléments de type `char` sous la forme d'un objet `string`.|  
|[wstring](../Topic/wstring.md)|Type qui décrit une spécialisation de la classe de modèle `basic_string` avec des éléments de type `wchar_t` sous la forme d'un objet `wstring`.|  
|[u16string](../Topic/u16string.md)|Type qui décrit une spécialisation de la classe de modèle `basic_string` basée sur des éléments de type `char16_t`.|  
|[u32string](../Topic/u32string.md)|Type qui décrit une spécialisation de la classe de modèle `basic_string` basée sur des éléments de type `char32_t`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \+](../Topic/operator+%20\(%3Cstring%3E\).md)|Concatène deux objets string.|  
|[operator\!\=](../Topic/operator!=%20\(%3Cstring%3E\).md)|Teste si l'objet string situé à gauche de l'opérateur n'est pas égal à l'objet string situé à droite.|  
|[operator\=\=](../Topic/operator==%20\(%3Cstring%3E\).md)|Teste si l'objet string situé à gauche de l'opérateur est égal à l'objet string situé à droite.|  
|[\< \(opérateur\)](../Topic/operator%3C%20\(%3Cstring%3E\).md)|Teste si l'objet string situé à gauche de l'opérateur est inférieur à l'objet string situé à droite.|  
|[\<\= \(opérateur\)](../Topic/operator%3C=%20\(in%20%3Cstring%3E\).md)|Teste si l'objet string situé à gauche de l'opérateur est inférieur ou égal à l'objet string situé à droite.|  
|[\<\<, opérateur](../Topic/operator%3C%3C%20\(%3Cstring%3E\).md)|Fonction de modèle qui insère une chaîne dans le flux de sortie.|  
|[\> \(opérateur\)](../Topic/operator%3E%20\(%3Cstring%3E\).md)|Teste si l'objet string situé à gauche de l'opérateur est supérieur à l'objet string situé à droite.|  
|[\>\= \(opérateur\)](../Topic/operator%3E=%20\(%3Cstring%3E\).md)|Teste si l'objet string situé à gauche de l'opérateur est supérieur ou égal à l'objet string situé à droite.|  
|[\>\>, opérateur](../Topic/operator%3E%3E%20\(%3Cstring%3E\).md)|Fonction de modèle qui extrait une chaîne du flux d'entrée.|  
  
### Fonctions avec modèle spécialisé  
  
|||  
|-|-|  
|[échange](../Topic/swap%20\(C++%20STL%20%3Cstring%3E\).md)|Échange les tableaux de caractères de deux chaînes.|  
|[stod](../Topic/stod.md)|Convertit une séquence de caractères en `double.`.|  
|[stof](../Topic/stof.md)|Convertit une séquence de caractères en `float`.|  
|[stoi](../Topic/stoi.md)|Convertit une séquence de caractères en entier.|  
|[stold](../Topic/stold.md)|Convertit une séquence de caractères en `long double`.|  
|[stoll](../Topic/stoll.md)|Convertit une séquence de caractères en `long long`.|  
|[stoul](../Topic/stoul.md)|Convertit une séquence de caractères en `unsigned long`.|  
|[stoull](../Topic/stoull.md)|Convertit une séquence de caractères en `unsigned long long`.|  
|[to\_string](../Topic/to_string.md)|Convertit une valeur en `string`.|  
|[to\_wstring](../Topic/to_wstring.md)|Convertit une valeur en `string` large.|  
  
### Fonctions  
  
|||  
|-|-|  
|[getline](../Topic/getline%20Template%20Function.md)|Extrait des chaînes du flux d'entrée, ligne par ligne.|  
  
### Classes  
  
|||  
|-|-|  
|[basic\_string, classe](../standard-library/basic-string-class.md)|Classe de modèle qui décrit les objets pouvant stocker une séquence d'objets de type caractère arbitraires.|  
|[char\_traits, struct](../standard-library/char-traits-struct.md)|Classe de modèle qui décrit les attributs associés à un caractère de type CharType|  
  
### Spécialisations  
  
|||  
|-|-|  
|[char\_traits\<char\>, struct](../standard-library/char-traits-char-struct.md)|Struct qui est une spécialisation de la structure de modèle `char_traits`\<CharType\> d'un élément de type `char`.|  
|[char\_traits\<wchar\_t\>, struct](../standard-library/char-traits-wchar-t-struct.md)|Struct qui est une spécialisation de la structure de modèle `char_traits`\<CharType\> d'un élément de type `wchar_t`.|  
|[char\_traits\<char16\_t\>, struct](../standard-library/char-traits-char16-t-struct.md)|Struct qui est une spécialisation de la structure de modèle `char_traits`\<CharType\> d'un élément de type `char16_t`.|  
|[char\_traits\<char32\_t\>, struct](../standard-library/char-traits-char32-t-struct.md)|Struct qui est une spécialisation de la structure de modèle `char_traits`\<CharType\> d'un élément de type `char32_t`.|  
  
## Configuration requise  
  
-   **En\-tête :** \<string\>  
  
-   **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)