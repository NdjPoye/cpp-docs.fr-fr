---
title: "Basic CString Operations | Microsoft Docs"
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
  - "caractères, accessing in CStrings"
  - "CString objects"
  - "CString objects, opérations de base"
  - "literal strings, CString operations"
  - "comparaison de chaînes, CString operations"
  - "littéraux de chaîne, CString operations"
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Basic CString Operations
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit les opérations de base de [CString](../atl-mfc-shared/reference/cstringt-class.md) suivantes :  
  
-   [Créer des objets de CString des chaînes littérales C standard](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
-   [Différents caractères d'accès dans un CString](#_core_accessing_individual_characters_in_a_cstring)  
  
-   [Concaténer deux objets de CString](#_core_concatenating_two_cstring_objects)  
  
-   [Comparer des objets de CString](#_core_comparing_cstring_objects)  
  
-   [Convertir les objets de CString](#_core_converting_cstring_objects)  
  
 `Class CString` est basé sur le modèle de classe [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md).  `CString` est `typedef` d' `CStringT`.  Plus précisément, `CString` est `typedef`*d'une spécialisation explicite* d' `CStringT`, qui est un moyen courant d'utiliser un modèle de classe pour définir une classe.  Les classes de même sont définies `CStringA` et `CStringW`.  Pour plus d'informations sur la spécialisation explicite, consultez [Instanciation du modèle de classe](../Topic/Class%20Template%20Instantiation.md).  
  
 `CString`, `CStringA`, et `CStringW` sont définis dans atlstr.h.  `CStringT` est défini dans cstringt.h.  
  
 `CString`, `CStringA`, et `CStringW` chaque obtenir un ensemble de méthodes et les opérateurs définis par `CStringT` à utiliser avec les données de chaîne qu'ils prennent en charge.  Une partie du double de méthodes et, dans certains cas, surpasse les services de chaîne des bibliothèques runtime C.  
  
 Remarque : `CString` est une classe native.  Pour une classe de chaîne qui est à utiliser dans le projet géré par \+\+\/CLI c, utilisez `System.String`.  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> Créer des objets de CString des chaînes littérales C standard  
 Vous pouvez assigner des chaînes littérales de style C à `CString` de même que vous pouvez assigner un objet d' `CString` à un autre.  
  
-   Assignez la valeur de la chaîne littérale c à un objet d' `CString` .  
  
     [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_1.cpp)]  
  
-   Assignez la valeur d'un `CString` à un autre objet d' `CString` .  
  
     [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_2.cpp)]  
  
     Le contenu d'un objet d' `CString` est copié lorsqu'un objet d' `CString` est assigné à un autre.  Par conséquent, les deux chaînes ne partagent pas une référence aux caractères réels qui composent la chaîne.  Pour plus d'informations sur l'utilisation des objets d' `CString` comme valeurs, consultez [CString Semantics](../atl-mfc-shared/cstring-semantics.md).  
  
    > [!NOTE]
    >  Pour écrire votre application afin qu'elle puisse être compilée pour Unicode ou pour ANSI, chaînes littérales de code à l'aide de la macro de \_T.  Pour plus d'informations, consultez [Prise en charge des jeux de caractères Unicode et MBCS \(Multibyte Character Set\)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> Différents caractères d'accès dans un CString  
 Vous pouvez accéder aux différents caractères d'un objet d' `CString` à l'aide de les méthodes d' `GetAt` et d' `SetAt` .  Vous pouvez également utiliser l'élément de tableau, ou indice, opérateur \(\[\]\) au lieu d' `GetAt` pour obtenir des caractères.  \(Cela ressemble aux éléments de tableau à accéder par index, comme dans les chaînes de style C standard.\) Les valeurs d'index des caractères d' `CString` sont de base zéro.  
  
##  <a name="_core_concatenating_two_cstring_objects"></a> Concaténer deux objets de CString  
 Pour concaténer deux objets d' `CString` , utilisez les opérateurs de concaténation \(\+ ou \+\), comme suit.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_3.cpp)]  
  
 Au moins un argument aux opérateurs de concaténation \(\+ ou \+\) doit être un objet d' `CString` , mais vous pouvez utiliser une chaîne constante \(par exemple, `"big"`\) ou un `char` \(par exemple, « x "\) pour l'autre argument.  
  
##  <a name="_core_comparing_cstring_objects"></a> Comparer des objets de CString  
 La méthode d' `Compare` et l'opérateur de \=\= pour `CString` sont identiques.  `Compare`, `operator==`, et `CompareNoCase` sont MBCS et Unicode avertis ; `CompareNoCase` est également la casse.  La méthode d' `Collate` d' `CString` est sensible aux paramètres régionaux et est souvent plus lent qu' `Compare`.  Utilisez `Collate` uniquement lorsque vous devez respecter les règles de tri comme spécifié par les paramètres régionaux.  
  
 Le tableau suivant montre les fonctions de comparaison disponibles de [CString](../atl-mfc-shared/reference/cstringt-class.md) et leur équivalent Unicode\/MBCS\-portable fonctions de la bibliothèque Runtime C.  
  
|Fonction de CString|Fonctions MBCS|Fonction Unicode|  
|-------------------------|--------------------|----------------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 Le modèle de classe d' `CStringT` définit les opérateurs relationnels \(\<, \<\=, \>\=, \>, \=\=, et \! \=\), qui sont disponibles pour une utilisation par d' `CString`.  Vous pouvez comparer deux `CStrings` à l'aide de ces opérateurs, comme indiqué dans l'exemple suivant.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_4.cpp)]  
  
##  <a name="_core_converting_cstring_objects"></a> Convertir les objets de CString  
 Pour plus d'informations sur la conversion des objets de CString à d'autres types de chaînes, consultez [Comment : effectuer une conversion entre différents types de chaînes](../text/how-to-convert-between-various-string-types.md).  
  
## À l'aide de CString avec le wcout  
 Pour utiliser un CString avec `wcout` vous devez caster explicitement l'objet à `const wchar_t*` comme indiqué dans l'exemple suivant :  
  
```  
CString cs("meow");  
  wcout << (const wchar_t*) cs << endl;  
  
```  
  
 Sans cast, `cs` est traité comme `void*` et `wcout` imprime l'adresse de l'objet.  Ce comportement est provoqué par les interactions subtiles entre la déduction d'arguments template et la résolution de surcharge qui sont dans elles\-mêmes corrects et conforme à la norme C\+\+.  
  
## Voir aussi  
 [Chaînes](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)   
 [Instanciation du modèle de classe](../Topic/Class%20Template%20Instantiation.md)   
 [Spécialisation explicite des modèles de classe](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)   
 [Spécialisation partielle des modèles de classe](../cpp/template-specialization-cpp.md)   
 [Comment : effectuer une conversion entre différents types de chaînes](../text/how-to-convert-between-various-string-types.md)