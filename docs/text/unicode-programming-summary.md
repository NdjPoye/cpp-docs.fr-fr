---
title: "Synth&#232;se de la programmation Unicode | Microsoft Docs"
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
  - "Unicode (C++), fonctions runtime MFC et C"
  - "Unicode (C++), programmer avec"
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Synth&#232;se de la programmation Unicode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour tirer parti de la prise en charge MFC et de la bibliothèque Runtime C pour Unicode, vous devez :  
  
-   Définir **\_UNICODE**.  
  
     Définissez le symbole **\_UNICODE** avant de générer votre programme.  
  
-   Spécifier un point d'entrée.  
  
     Dans la page **Sortie** du dossier Éditeur de liens de la boîte de dialogue [Pages de propriétés](../ide/property-pages-visual-cpp.md) du projet, définissez le symbole de point d'entrée à **wWinMainCRTStartup**.  
  
-   Utiliser des fonctions et des types portables.  
  
     Utilisez les fonctions runtime C correctes pour la gestion des chaînes Unicode.  Vous pouvez utiliser la famille de fonctions **wcs**, mais vous pouvez préférer les macros portables **\_TCHAR** \(compatible pour l'internationale\).  Ces macros utilisent un préfixe **\_tcs** et remplacent les fonctions de la famille **str**.  Ces fonctions sont décrites en détail dans la section [Internationalisation](../c-runtime-library/internationalization.md) de *la référence de la bibliothèque Runtime*.  Pour plus d'informations, consultez [Mappages de texte générique dans Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
     Utilisez **\_TCHAR** et les types de données portables associées décrites dans [Prise en charge pour Unicode](../text/support-for-unicode.md).  
  
-   Gérer les chaînes littérales correctement.  
  
     Le compilateur Visual C\+\+ interprète une chaîne littérale codée comme suit :  
  
    ```  
    L"this is a literal string"  
    ```  
  
     pour indiquer une chaîne de caractères Unicode.  Vous pouvez utiliser le même préfixe pour les caractères littéraux.  Utilisez la macro **\_T** pour coder les chaînes littérales génériquement, afin qu'elles soient compilées en tant que chaînes Unicode sous Unicode ou en tant que chaînes ANSI \(y compris MBCS\) sans Unicode.  Par exemple, au lieu de :  
  
    ```  
    pWnd->SetWindowText( "Hello" );  
    ```  
  
     utilisez :  
  
    ```  
    pWnd->SetWindowText( _T("Hello") );  
    ```  
  
     Lorsque **\_UNICODE** est défini, **\_T** traduit la chaîne littérale en formulaire avec un préfixe L, dans le cas contraire, **\_T** traduit la chaîne sans préfixe L.  
  
    > [!TIP]
    >  La macro **\_T** est identique à la macro `_TEXT`.  
  
-   Faire attention lorsque vous passez des longueurs de chaînes aux fonctions.  
  
     Certaines fonctions utilisent le nombre de caractères d'une chaîne, d'autres le nombre d'octets.  Par exemple, si **\_UNICODE** est défini, l'appel suivant à l'objet `CArchive` ne fonctionnera pas \(`str` est un `CString`\) :  
  
    ```  
    archive.Write( str, str.GetLength( ) );    // invalid  
    ```  
  
     Dans une application Unicode, la longueur vous donne le nombre de caractères mais pas le nombre correct d'octets, dans la mesure où chaque caractère utilise deux octets.  Vous devez utiliser :  
  
    ```  
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid  
    ```  
  
     qui indique le nombre correct d'octets à écrire.  
  
     Cependant, les fonctions membres MFC orientées caractère, plutôt qu'octet, fonctionnent sans codage supplémentaire :  
  
    ```  
    pDC->TextOut( str, str.GetLength( ) );  
    ```  
  
     `CDC::TextOut` prend un nombre de caractères et non un nombre d'octets.  
  
-   Utilisez [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) pour ouvrir des fichiers Unicode.  
  
 Pour résumer, MFC et la bibliothèque Runtime fournissent la prise en charge suivante pour la programmation Unicode sous Windows 2000 :  
  
-   Sauf pour les fonctions membre de classe de base de données, toutes les fonctions MFC sont activées par Unicode, notamment `CString`.  `CString` fournit également des fonctions de conversion Unicode\/ANSI.  
  
-   La bibliothèque Runtime fournit les versions Unicode de toutes les fonctions de gestion de chaînes. \(La bibliothèque Runtime fournit également des versions portables utilisables pour Unicode ou pour MBCS.  Il s'agit des macros **\_tcs**.\)  
  
-   Tchar.h fournit des types de données portables et la macro **\_T** pour la traduction des chaînes et des caractères de type littéral.  Pour plus d'informations, consultez [Mappages de texte générique dans Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
-   La bibliothèque Runtime fournit une version à caractère large de **main**.  Utilisez **wmain** afin que votre application devienne compatible Unicode.  
  
## Voir aussi  
 [Prise en charge pour Unicode](../text/support-for-unicode.md)