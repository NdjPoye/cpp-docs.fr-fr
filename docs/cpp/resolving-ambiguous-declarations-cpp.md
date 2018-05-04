---
title: Résolution des déclarations ambiguës (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 530111ee439a991201debab876d485a36b7f5ac5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="resolving-ambiguous-declarations-c"></a>Résolution des déclarations ambiguës (C++)
Pour exécuter des conversions explicites d'un type en un autre, vous devez utiliser des casts, en spécifiant le nom de type voulu. Certains casts de type entraînent une ambiguïté syntaxique. Le cast de type de style fonction suivant est ambigu :  
  
```  
char *aName( String( s ) );  
```  
  
 Il est difficile de savoir s’il s’agit d’une déclaration de fonction ou une déclaration d’objet avec un cast de style fonction comme initialiseur : il peut déclarer une fonction qui retourne le type **char \***  qui prend un argument de type `String` , ou il peut déclarer l’objet `aName` et l’initialiser avec la valeur de `s` castée en type `String`.  
  
 Si une déclaration peut être considérée comme une déclaration de fonction valide, elle est traitée comme telle. Une instruction est examinée pour voir s'il s'agit d'un cast de type de style fonction seulement si ce peut être une déclaration de fonction, c'est-à-dire si elle serait syntaxiquement incorrecte. Par conséquent, le compilateur considère l'instruction comme une déclaration d'une fonction et ignore les parenthèses autour de l'identificateur `s`. En revanche, les instructions :  
  
```  
char *aName( (String)s );  
```  
  
 et  
  
```  
char *aName = String( s );  
```  
  
 sont clairement des déclarations d’objets et une conversion définie par l’utilisateur à partir du type `String` au type **char \***  est appelée pour effectuer l’initialisation de `aName`.  
  
## <a name="see-also"></a>Voir aussi  
 