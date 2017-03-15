---
title: "String Data Management | Microsoft Docs"
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
  - "Unicode, string objects"
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# String Data Management
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ propose plusieurs manières de gérer des données de chaîne :  
  
-   [Manipulation de chaînes](../c-runtime-library/string-manipulation-crt.md) pour travailler avec des chaînes terminée par le caractère NULL de style C  
  
-   L'API Win32 s'exécute pour la gestion des chaînes  
  
-   La classe [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)MFC, qui fournit les objets String flexibles et redimensionnables  
  
-   Classe [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md), qui fournit un objet chaîne par MFC indépendant les mêmes fonctionnalités que `CString`  
  
 Presque tous les programmes utilisent des données de chaîne.  La classe d' `CString` MFC est souvent la meilleure solution pour la gestion flexible de chaîne.  Depuis la version 7,0, `CString` peut être utilisé dans MFC ou des programmes par MFC indépendants.  La bibliothèque Runtime et la prise en charge d' `CString` chaînes contenir des caractères  \(larges\) multioctets, en Unicode ou la programmation MBCS.  
  
 Cet article décrit des services à caractère général que la bibliothèque de classes fournit associé à la manipulation de chaînes.  Les rubriques couverts dans cet article incluent :  
  
-   [Unicode et MBCS fournissent la portabilité](#_core_unicode_and_mbcs_provide_portability)  
  
-   [CStrings et pointeurs const char](#_core_cstrings_and_const_char_pointers)  
  
-   [Décompte de références de CString](#_core_cstring_reference_counting)  
  
 La classe de [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) prend en charge la manipulation des chaînes.  Elle est conçue pour substituer et étendre la fonctionnalité normalement fournie par le module de chaîne de la bibliothèque Runtime C.  Les fonctions membres et les opérateurs de fournit de classe d' `CString` pour la gestion simplifiée de chaîne, semblables à ceux trouvés dans de base.  La classe fournit également des constructeurs et des opérateurs pour construire, assigner, et comparer **CStrings** et les types de données string C\+\+ standard.  Étant donné qu' `CString` n'est pas dérivé d' `CObject`, vous pouvez utiliser des objets d' `CString` indépendamment de la plupart de la bibliothèque MFC \(microsoft foundation class\).  
  
 Les objets d'`CString` suivent la sémantique « value ». Un objet d' `CString` représente une valeur unique.  Pensez à `CString` comme une chaîne réelle, et non en tant que pointeur vers une chaîne.  
  
 Un objet d' `CString` représente une séquence d'un nombre variable de caractères.  Les objets d'`CString` peuvent être considérés comme des tableaux de caractères.  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a> Unicode et MBCS fournissent la portabilité  
 Avec la version 3,0 de MFC et versions ultérieures, MFC, notamment `CString`, est activé pour Unicode et les jeux de caractères multioctets \(MBCS\).  Cette prise en charge le plus facile pour vous permettre d'écrire des applications mobiles que vous pouvez générer pour Unicode ou des caractères ANSI.  Pour activer cette portabilité, chaque caractère d'un objet d' `CString` est du type **TCHAR**, défini comme `wchar_t` si vous définissez le symbole **\_UNICODE** lorsque vous générez votre application, ou comme `char` cas contraire.  Un caractère d' `wchar_t` est 16 bits de large.  MBCS est activé si vous générez avec le symbole **\_MBCS** défini.  MFC elle\-même est généré avec le symbole de **\_MBCS** \(pour les bibliothèques de NAFX\) ou le symbole de **\_UNICODE** \(pour les bibliothèques d'UAFX\) défini.  
  
> [!NOTE]
>  Les exemples d' `CString` dans cette et les éléments accompagnants sur les chaînes affichent des chaînes littérales correctement mises en forme pour la portabilité Unicode, à l'aide de la macro de **\_T** , ce qui convertit la chaîne littérale au formulaire :  
  
 `L"literal string"`  
  
> [!NOTE]
>  le compilateur traite comme une chaîne Unicode.  Par exemple, le code suivant :  
  
 [!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/CPP/string-data-management_1.cpp)]  
  
> [!NOTE]
>  est traduit en tant que chaîne Unicode si **\_UNICODE** est défini ou comme une chaîne ANSI dans le cas contraire.  Pour plus d'informations, consultez l'article [Prise en charge des jeux de caractères Unicode et MBCS \(Multibyte Character Set\)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
 Un objet d' `CString` peut stocker jusqu'à **INT\_MAX** \(2.147.483.647\) caractères.  Le type de données de **TCHAR** est utilisé pour obtenir ou définir les différents caractères à l'intérieur de `CString` objet.  Contrairement aux tableaux de caractères, la classe d' `CString` une capacité d'allocation de mémoire interne.  Cela permet aux objets d' `CString` pour développer automatiquement en fonction de les besoins \(autrement dit, vous n'avez pas à vous préoccuper d'élever un objet d' `CString` sur de longues chaînes convenables\).  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a> CStrings et pointeurs const char  
 Un objet d' `CString` peut également agir comme une chaîne de style C littérale \( `PCXSTR`, qui est la même que **const char\*** sinon sous Unicode\).  L'opérateur de conversion de [CSimpleStringT::operator PCXSTR](../Topic/CSimpleStringT::operator%20PCXSTR.md) permet aux objets d' `CString` à substituer librement pour les pointeurs de caractères dans les appels de fonction.  Le constructeur de **CString\( LPCWSTR**`pszSrc`**\)** permet aux pointeurs de caractères à remplacer des objets d' `CString` .  
  
 Aucune tentative n'est faite pour plier des objets d' `CString` .  Si vous avez deux objets d' `CString` contenant `Chicago`, par exemple, les caractères dans `Chicago` sont stockés dans deux emplacements.  \(Cela ne peut pas être vrai les versions ultérieures de MFC, vous ne devez pas dépendre de lui.\)  
  
> [!NOTE]
>  Utilisez les fonctions membres de [CSimpleStringT::GetBuffer](../Topic/CSimpleStringT::GetBuffer.md) et de [CSimpleStringT::ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md) lorsque vous devez accéder directement à `CString` en tant que pointeur non constante à un caractère.  
  
> [!NOTE]
>  Utilisez les fonctions membres de [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md) et de [CStringT::SetSysString](../Topic/CStringT::SetSysString.md) pour allouer et pour définir des objets d' `BSTR` utilisés dans l'automation \(précédemment appelé OLE Automation\).  
  
> [!NOTE]
>  Dans la mesure du possible, allouez les objets d' `CString` sur le frame plutôt que sur le tas.  Cela permet d'économiser de la mémoire et simplifie le passage de paramètres.  
  
 La classe d' `CString` n'est pas implémentée comme une classe de collection de bibliothèque MFC, bien que les objets d' `CString` certainement puissent être enregistrés en tant qu'éléments dans les collections.  
  
##  <a name="_core_cstring_reference_counting"></a> Décompte de références de CString  
 As of la version 4,0 des MFC, lorsque les objets de [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) sont copiés, MFC incrémente le décompte de références plutôt que la copie des données.  Cela fait passer des paramètres par valeur et retourner des objets d' `CString` par la valeur plus efficace.  Ces opérations entraînent le constructeur de copie d'être appelé, parfois plusieurs fois.  Incrémentant un décompte de références réduit de charge pour ces opérations communes et effectue à l'aide de `CString` une option plus attrayante.  
  
 Chaque fois qu'une copie est détruite, le nombre de références de l'objet d'origine est décrémenté.  L'objet d' `CString` d'origine n'est pas détruit jusqu'à ce que son décompte de références est réduit à zéro.  
  
 Vous pouvez utiliser les fonctions membres [CSimpleStringT::LockBuffer](../Topic/CSimpleStringT::LockBuffer.md) et [CSimpleStringT::UnlockBuffer](../Topic/CSimpleStringT::UnlockBuffer.md) d' `CString` pour désactiver ou activer le décompte de références.  
  
## Voir aussi  
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)