---
title: char, wchar_t, char16_t, char32_t | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs: C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4eaccef4253d2b677f01801b680bb94d8a4d3516
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
Les types char, wchar_t, char16_t et char32_t sont des types intégrés qui représentent des caractères alphanumériques, ainsi que des glyphes non alphanumériques et des caractères non imprimables. char a une taille de huit bits, wchar_t et char16_t ont une taille de 16 bits et char32_t a une taille de 32 bits.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
char     ch1{ 'a' };    
wchar_t  ch2{ 'a' }; // or {L'a'}    
char16_t ch3{ L'a' };// or {L'a'}    
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## <a name="remarks"></a>Remarques  
 Le type `char` était le type de caractère d'origine en C et C++. Il peut être utilisé pour stocker des caractères du jeu de caractères ASCII, de l'un des jeux de caractères ISO-8859 ou du jeu de caractères UTF-8. Le type `unsigned char` est souvent utilisée pour représenter un *octets* qui n’est pas un type intégré en C++. Le type char n'est pas adapté au texte dans de nombreuses langues. En général, les programmes modernes doivent utiliser l'un des types à caractères larges pour représenter du texte. Unicode est le  
  
 Dans la bibliothèque standard C++, le type basic_string est spécialisé pour les chaînes étroites et étendues. Utilisez std::string quand les caractères sont de type char et std::wstring quand les caractères sont de type wchar_t. D'autres types qui représentent du texte, y compris std::stringstream et std::cout ont des spécialisations pour les chaînes étroites et étendues.  
  
