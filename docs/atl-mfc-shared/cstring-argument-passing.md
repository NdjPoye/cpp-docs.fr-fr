---
title: "CString Argument Passing | Microsoft Docs"
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
  - "argument passing [C++]"
  - "argument passing [C++], C strings"
  - "arguments [C++], passer"
  - "CString objects, passer des arguments"
  - "fonctions (C++), strings as input/output"
  - "passer des arguments, C strings"
  - "string arguments"
  - "chaînes (C++), as function input/output"
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CString Argument Passing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment passer des objets de [CString](../atl-mfc-shared/reference/cstringt-class.md) aux fonctions et comment retourner des objets d' `CString` des fonctions.  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a> Conventions Argument\-Passantes de CString  
 Lorsque vous définissez une interface de classe, vous devez déterminer la convention argument\- passante pour les fonctions membres.  Il existe quelques règles standard pour passer et retourner des objets d' `CString` .  Si vous suivez les règles décrites dans [Chaînes comme entrées de fonction](#_core_strings_as_function_inputs) et [Chaînes comme sortie de fonction](#_core_strings_as_function_outputs), vous aurez un code efficace et correct.  
  
##  <a name="_core_strings_as_function_inputs"></a> Chaînes comme entrées de fonction  
 Le plus efficace et la manière sécurisée d'utiliser un objet d' `CString` dans les fonctions appelées est de passer un objet d' `CString` à la fonction.  En dépit de nom, un objet d' `CString` ne stocke pas une chaîne en interne comme une chaîne de style c qui a une marque de fin null.  En fait, un objet d' `CString` garde la trace minutieuse du nombre de caractères qu'il possède.  En ayant `CString` fournissez un pointeur d' `LPCTSTR` à une chaîne terminée par le caractère NULL est une petite quantité de travail qui peut devenir significatif si votre code doit le faire constamment.  Le résultat est temporaire car toute modification apportée au contenu d' `CString` invalide les copies anciennes du pointeur d' `LPCTSTR` .  
  
 Il est logique dans certains cas de fournir le tableau de chaînes de style.  Par exemple, il peut y avoir une situation où une fonction appelée est écrite en C et ne prend pas en charge les objets.  Dans ce cas, forcer le paramètre d' `CString` à `LPCTSTR`, et la fonction obtiendra à c la chaîne terminée par le caractère NULL de style.  Vous pouvez également passer l'autre direction et créer un objet d' `CString` à l'aide de le constructeur d' `CString` qui accepte le paramètre de chaîne de style c.  
  
 Si le contenu de la chaîne doit être modifié par une fonction, déclarez le paramètre comme référence non constante d' `CString` \(**CString&**\).  
  
##  <a name="_core_strings_as_function_outputs"></a> Chaînes comme sortie de fonction  
 En général vous pouvez retourner des objets d' `CString` des fonctions car les objets d' `CString` suivent la sémantique de valeur comme des types primitifs.  Pour retourner une chaîne en lecture seule, utilisez une référence à une constante d' `CString` \(**const CString&**\).  L'exemple suivant illustre l'utilisation des paramètres et des types de retour d' `CString` :  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/CPP/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/CPP/cstring-argument-passing_2.cpp)]  
  
## Voir aussi  
 [Chaînes](../atl-mfc-shared/strings-atl-mfc.md)