---
title: "Prise en charge des jeux de caract&#232;res Unicode et MBCS (Multibyte Character Set) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC [C++], prise en charge des jeux de caractères"
  - "MBCS [C++], chaînes et prise en charge de MFC"
  - "chaînes[C++], prise en charge de MBCS dans MFC"
  - "jeux de caractères [C++], multioctets"
  - "Unicode [C++], chaînes MFC"
  - "Unicode [C++], objets de chaîne"
  - "chaînes [C++], Unicode"
  - "chaînes [C++], prise en charge des jeux de caractères"
ms.assetid: 44b3193b-c92d-40c5-9fa8-5774da303cce
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Prise en charge des jeux de caract&#232;res Unicode et MBCS (Multibyte Character Set)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Certains langages, par exemple, japonais et chinois, ont des jeux de caractères de grande taille.  Pour prendre en charge la programmation pour ces marchés, la bibliothèque MFC \(Microsoft Foundation Class\) est activée pour deux gestions différentes des grands jeux de caractères :  
  
-   [Unicode](#_core_mfc_support_for_unicode_strings)  
  
-   [MBCS \(Jeux de Caractère Multi\-Octets\)](#_core_mfc_support_for_mbcs_strings)  
  
 Vous devez utiliser Unicode pout tout nouveau développement.  
  
##  <a name="_core_mfc_support_for_unicode_strings"></a> Prise en charge MFC pour les chaînes Unicode  
 L'entière bibliothèque de classes est conditionnellement activée pour les caractères Unicode et les chaînes.  En particulier, la classe [CString](../atl-mfc-shared/reference/cstringt-class.md) est activée pour Unicode.  
  
|||||  
|-|-|-|-|  
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|  
|MFC*xx*U.LIB|MFC*xx*U.PDB|MFC*xx*U.DLL|MFC*xx*UD.LIB|  
|MFC*xx*UD.PDB|MFC*xx*UD.DLL|MFCS*xx*U.LIB|MFCS*xx*U.PDB|  
|MFCS*xx*UD.LIB|MFCS*xx*UD.PDB|MFCM*xx*U.LIB|MFCM*xx*U.PDB|  
|MFCM*xx*U.DLL|MFCM*xx*UD.LIB|MFCM*xx*UD.PDB|MFCM*xx*UD.DLL|  
  
 \(*xx* représente le numéro de version du fichier ; par exemple, « 80 " signifie la version 8,0.\)  
  
 `CString` est basé sur le type de données `TCHAR`.  Si le symbole `_UNICODE` est défini pour une version de votre programme, `TCHAR` est défini comme type `wchar_t`, un type 16 bits d'encodage de caractères.  Sinon, `TCHAR` est défini comme `char`, l'encodage 8 bits normal.  Par conséquent, sous Unicode, `CString` est composé de caractères 16 bits.  Sans Unicode, il est constitué de caractères de type `char`.  
  
 Pour terminer la programmation Unicode de votre application, vous devez aussi :  
  
-   Utilisez cette macro `_T` pour coder de manière conditionnelle vos chaînes littérales telles qu'elles soient portables au format Unicode.  
  
-   Lorsque vous passez vos chaînes, regardez bien si les arguments de fonction requièrent une longueur de caractères ou une longueur en octets.  La différence est importante si vous utilisez des chaînes Unicode.  
  
-   Utilisez les versions portables d'utilisation de la gestion de fonctions du moteur d'éxécution C.  
  
-   Utilisez les types de données suivantes pour les caractères et les pointeurs de caractères :  
  
    -   `TCHAR` Où vous utiliseriez `char`.  
  
    -   `LPTSTR` Où vous utiliseriez `char*`.  
  
    -   `LPCTSTR` Où vous utiliseriez `const char*`.  `CString` fournit l'opérateur `LPCTSTR` pour convertir entre `CString` et `LPCTSTR`.  
  
 `CString` fournit également des constructeurs, des opérateurs d'assignation, et des opérateurs de comparaison sans Unicode.  
  
 Pour plus d'informations sur la programmation Unicode, consultez [Rubriques Unicode](../mfc/unicode-in-mfc.md).  [Référence de la bibliothèque Runtime](../c-runtime-library/c-run-time-library-reference.md) définit les versions portables de toutes ses fonctions de gestion.  Consultez la catégorie [Internationalisation](../c-runtime-library/internationalization.md).  
  
##  <a name="_core_mfc_support_for_mbcs_strings"></a> Prise en charge MFC des chaînes MBCS  
  
> [!WARNING]
>  Les chaînes MBCS sont technologiquement héritée et ne doivent pas être utilisées dans de nouveaux projets.  Les informations suivantes sont fournies pour les scénarios dans lesquels vous devez conserver un code existant qui utilise MBCS et s'il n'est pas possible de mettre le code à niveau pour utiliser Unicode.  
  
 La bibliothèque de classes est également activée pour les jeux de caractères multi\-octets, mais uniquement pour les jeux de caractères codés sur deux octets \(DBCS\).  
  
> [!IMPORTANT]
>  Dans [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] et versions ultérieures, les versions MBCS des DLL MFC sont disponibles comme complément libre à Visual Studio depuis le site de téléchargement MSDN.  Pour plus d’informations, consultez [Compléments des DLL MBCS et MFC](../mfc/mfc-mbcs-dll-add-on.md).  
  
 Dans un jeu de caractères multi\-octets, la largeur d'un caractère peut être un ou deux octets.  S'il est large de deux octets, son premier octet est un « octet de tête » spécial qui est choisi depuis une plage spécifique, choisie selon la page de codes utilisée.  Ensemble, les octets de tête et « les octets de queue » spécifient un seul encodage de caractères.  
  
 Si le symbole `_MBCS` est défini pour une version de votre programme, taper `TCHAR`, dans lequel `CString` est basé, correspond à `char`.  Il vous appartient de déterminer les octets dans `CString` sont des octets de tête et lesquels sont des octets de queue.  La bibliothèque Runtime C fournit des fonctions pour vous aider à déterminer ceci.  
  
 Sous DBCS, une chaîne donnée peut contenir tous les caractères ANSI codés sur un octet, tous les caractères codés sur deux octets, ou une combinaison des deux.  Ces fonctionnalités requièrent une attention particulière pour les chaînes d'analyse.  Cela inclut des objets `CString`.  
  
> [!NOTE]
>  La sérialisation de chaîne Unicode dans MFC peut lire à la fois les chaînes Unicode et les chaînes MBCS indépendamment de la version de l'application que vous exécutez.  Vos fichiers de données sont portables entre les versions Unicode et MBCS de votre programme.  
  
 Les fonctions du membre `CString` utilisent des versions spéciales de « texte générique » des fonctions du moteur d'éxécution C qu'elles appellent, ou elles utilisent des fonctions Unicode en charge.  Par conséquent, par exemple, si une fonction `CString` appellerait généralement `strcmp`, elle appelle la fonction correspondante de texte générique `_tcscmp` à la place.  Selon la façon dont les symboles `_MBCS` et `_UNICODE` sont définis, `_tcscmp` mappe comme suit :  
  
|||  
|-|-|  
|`_MBCS` défini|`_mbscmp`|  
|`_UNICODE` défini|`wcscmp`|  
|Aucun symbole défini|`strcmp`|  
  
> [!NOTE]
>  Les symboles `_MBCS` et `_UNICODE` s'excluent mutuellement.  
  
 Vos mappages de fonction de texte générique pour toutes les routines à l'exécution de gestion sont traités dans [Référence sur les bibliothèques Runtime C](../c-runtime-library/c-run-time-library-reference.md).  En particulier, consultez [Internationalisation](../c-runtime-library/internationalization.md).  
  
 De même, les méthodes `CString` sont implémentées à l'aide des mappages « génériques » de type de données.  Pour activer MBCS et Unicode ensembles, MFC utilise `TCHAR` pour `char`, `LPTSTR` pour `char*`, et `LPCTSTR` pour `const char*`.  Ceux\-ci garantissent les mappages appropriés pour MBCS ou Unicode.  
  
## Voir aussi  
 [Chaînes](../atl-mfc-shared/strings-atl-mfc.md)   
 [Manipulation de chaînes](../c-runtime-library/string-manipulation-crt.md)