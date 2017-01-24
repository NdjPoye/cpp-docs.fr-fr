---
title: "char, wchar_t, char16_t, char32_t | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "char_cpp"
  - "char16_t_cpp"
  - "whchar_t_cpp"
  - "char32_t_cpp"
dev_langs: 
  - "C++"
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# char, wchar_t, char16_t, char32_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les types char, wchar\_t, char16\_t et char32\_t sont des types intégrés qui représentent des caractères alphanumériques, ainsi que des glyphes non alphanumériques et des caractères non imprimables.  char a une taille de huit bits, wchar\_t et char16\_t ont une taille de 16 bits et char32\_t a une taille de 32 bits.  
  
## Syntaxe  
  
```vb  
char     ch1{ 'a' };  
wchar_t  ch2{ 'a' }; // or {L'a'}  
char16_t ch3{ L'a' };// or {L'a'}  
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## Notes  
 Le type `char` était le type de caractère d'origine en C et C\+\+.  Il peut être utilisé pour stocker des caractères du jeu de caractères ASCII, de l'un des jeux de caractères ISO\-8859 ou du jeu de caractères UTF\-8.  Le type `unsigned char` est souvent utilisé pour représenter un *octet* qui n'est pas un type intégré en C\+\+.  Le type char n'est pas adapté au texte dans de nombreuses langues.  En général, les programmes modernes doivent utiliser l'un des types à caractères larges pour représenter du texte.  Unicode est le  
  
 Dans la bibliothèque standard C\+\+, le type basic\_string est spécialisé pour les chaînes étroites et étendues.  Utilisez std::string quand les caractères sont de type char et std::wstring quand les caractères sont de type wchar\_t.  D'autres types qui représentent du texte, y compris std::stringstream et std::cout ont des spécialisations pour les chaînes étroites et étendues.  
  
## Configuration requise