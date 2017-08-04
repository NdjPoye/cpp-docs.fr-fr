---
title: "Chaînes de langue | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: dfbd15b0da6e09b825a1562f006416e975603ab5
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="language-strings"></a>Language Strings
Les fonctions `setlocale` et `_create_locale` peuvent utiliser les langues prises en charge par l’API NLS Windows sur les systèmes d’exploitation qui n’utilisent pas la page de codes Unicode. Pour obtenir la liste des langues prises en charge par la version du système d’exploitation Windows, consultez [National Language Support (NLS) API Reference](http://msdn.microsoft.com/goglobal/bb896001.aspx). La chaîne de langue peut être une des valeurs des colonnes **Langue** et **Abréviation du nom de langue** de la liste des langues prises en charge. L’implémentation de la bibliothèque Runtime C prend également en charge ces chaînes de langue :  
  
|Chaîne de langue|Nom des paramètres régionaux équivalents|  
|---------------------|----------------------------|  
|american|fr-FR|  
|american english|fr-FR|  
|american-english|fr-FR|  
|australian|en-AU|  
|belgian|nl-BE|  
|canadian|en-CA|  
|chh|zh-HK|  
|chi|zh-SG|  
|chinois|zh|  
|chinese-hongkong|zh-HK|  
|chinese-simplified|zh-CN|  
|chinese-singapore|zh-SG|  
|chinese-traditional|zh-TW|  
|dutch-belgian|nl-BE|  
|english-american|fr-FR|  
|english-aus|en-AU|  
|english-belize|en-BZ|  
|english-can|en-CA|  
|english-caribbean|en-029|  
|english-ire|en-IE|  
|english-jamaica|en-JM|  
|english-nz|en-NZ|  
|english-south africa|en-ZA|  
|english-trinidad y tobago|en-TT|  
|english-uk|en-GB|  
|english-us|fr-FR|  
|english-usa|fr-FR|  
|french-belgian|fr-BE|  
|french-canadian|fr-CA|  
|french-luxembourg|fr-LU|  
|french-swiss|fr-CH|  
|german-austrian|de-AT|  
|german-lichtenstein|de-LI|  
|german-luxembourg|de-LU|  
|german-swiss|de-CH|  
|irish-english|en-IE|  
|italian-swiss|it-CH|  
|norvégien|non|  
|norwegian-bokmal|nb-NO|  
|norwegian-nynorsk|nn-NO|  
|portuguese-brazilian|pt-BR|  
|spanish-argentina|es-AR|  
|spanish-bolivia|es-BO|  
|spanish-chile|es-CL|  
|spanish-colombia|es-CO|  
|spanish-costa rica|es-CR|  
|spanish-dominican republic|es-DO|  
|spanish-ecuador|es-EC|  
|spanish-el salvador|es-SV|  
|spanish-guatemala|es-GT|  
|spanish-honduras|es-HN|  
|spanish-mexican|es-MX|  
|spanish-modern|es-ES|  
|spanish-nicaragua|es-NI|  
|spanish-panama|es-PA|  
|spanish-paraguay|es-PY|  
|spanish-peru|es-PE|  
|spanish-puerto rico|es-PR|  
|spanish-uruguay|es-UY|  
|spanish-venezuela|es-VE|  
|swedish-finland|sv-FI|  
|swiss|de-CH|  
|uk|en-GB|  
|us|fr-FR|  
|usa|fr-FR|  
  
## <a name="see-also"></a>Voir aussi  
 [Chaînes relatives aux noms, aux langues, au pays et à la région](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Chaînes pays/région](../c-runtime-library/country-region-strings.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
