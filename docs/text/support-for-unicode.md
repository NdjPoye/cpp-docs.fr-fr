---
title: "Prise en charge pour Unicode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "jeux de caractères (C++), Unicode"
  - "globalisation (C++), jeux de caractères"
  - "localisation (C++), jeux de caractères"
  - "types de données portables (MFC)"
  - "Unicode (C++)"
  - "Unicode (C++), installer la prise en charge"
  - "caractères larges (C++), à propos des caractères larges"
ms.assetid: 180f1d10-8543-4f79-85ce-293d3cb443bb
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# Prise en charge pour Unicode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unicode est une spécification permettant la prise en charge de tous les jeux de caractères, y compris ceux qui ne peuvent pas être représentés au moyen d'un seul octet.  Si vous programmez pour un marché international, nous vous recommandons d'utiliser Unicode ou des [jeux de caractères multioctets](../text/support-for-multibyte-character-sets-mbcss.md) \(MBCS\), ou de permettre à votre programme de s'adapter à l'une ou l'autre solution en modifiant un commutateur.  
  
 Un caractère large est un code de caractère multilingue de 2 octets.  Partout dans le monde, la plupart des caractères utilisés dans l'informatique moderne, y compris les symboles techniques et les caractères d'édition spéciaux, peuvent être représentés conformément à la spécification Unicode sous la forme d'un caractère large.  Les caractères qui ne peuvent pas être représentés sous la forme d'un seul caractère large peuvent être représentés dans une paire Unicode au moyen de la fonctionnalité de substitution Unicode.  Comme chaque caractère large présente une taille fixe de 16 bits, l'utilisation des caractères larges simplifie la programmation avec les jeux de caractères internationaux.  
  
 Une chaîne de caractères larges est représentée sous la forme d'un tableau **wchar\_t\[\]** et est pointée par un pointeur `wchar_t*`.  Il est possible de représenter tout caractère ASCII sous la forme d'un caractère large en lui ajoutant la lettre L comme préfixe.  Par exemple, L'\\0' est le caractère **NULL** large \(16 bits\) de fin.  De même, il est possible de représenter toute chaîne ASCII sous la forme d'un littéral de chaîne à caractères larges en ajoutant la lettre L comme préfixe au littéral ASCII \(L"Hello"\).  
  
 En règle générale, les caractères larges prennent plus d'espace en mémoire que les caractères multioctets mais sont plus rapides à traiter.  En outre, un seul paramètre régional peut être représenté à la fois dans un encodage multioctet, tandis que tous les jeux de caractères du monde sont représentés simultanément par la représentation Unicode.  
  
 Toute l'infrastructure MFC prend en charge la spécification Unicode, et MFC permet la prise en charge d'Unicode en utilisant des macros portables, comme illustré dans le tableau ci\-dessous.  
  
### Types de données portables dans MFC  
  
|Type de données non portables|Remplacé par cette macro|  
|-----------------------------------|------------------------------|  
|`char`|\_**TCHAR**|  
|**char\***, **LPSTR \(type de données Win32\)**|`LPTSTR`|  
|**const char\*, LPCSTR \(type de données Win32\)**|`LPCTSTR`|  
  
 La classe `CString` utilise **\_TCHAR** comme base et fournit des constructeurs et des opérateurs pour simplifier les conversions.  Il est possible d'écrire la plupart des opérations de chaînes pour Unicode en utilisant la même logique que celle utilisée pour traiter le jeu de caractères Windows ANSI, si ce n'est que l'unité d'opération élémentaire est un caractère de 16 bits à la place d'un octet de 8 bits.  Contrairement à l'utilisation de jeux de caractères multioctets, vous n'avez pas à \(et ne devriez pas\) traiter un caractère Unicode comme s'il s'agissait de deux octets distincts.  
  
## Que voulez\-vous faire ?  
  
-   [Installer la prise en charge d'Unicode via MFC](../mfc/unicode-in-mfc.md)  
  
-   [Activer Unicode dans mon programme](../text/international-enabling.md)  
  
-   [Activer Unicode et MBCS dans mon programme](../text/internationalization-strategies.md)  
  
-   [Utiliser Unicode pour créer un programme internationalisé](../text/unicode-programming-summary.md)  
  
-   [Découvrir les avantages d'Unicode, y compris comment Unicode peut rendre mon programme plus efficace sur Windows 2000](../text/benefits-of-character-set-portability.md)  
  
-   [Utiliser wmain pour passer des arguments à caractères larges à mon programme](../text/support-for-using-wmain.md)  
  
-   [Voir un résumé de la programmation Unicode](../text/unicode-programming-summary.md)  
  
-   [Découvrir les mappages de texte générique pour la portabilité de la largeur en octets](../text/generic-text-mappings-in-tchar-h.md)  
  
## Voir aussi  
 [Texte et chaînes](../text/text-and-strings-in-visual-cpp.md)   
 [Prise en charge de l'utilisation de wmain](../text/support-for-using-wmain.md)