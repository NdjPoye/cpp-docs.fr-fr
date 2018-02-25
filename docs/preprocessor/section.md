---
title: section | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- section_CPP
- vc-pragma.section
dev_langs:
- C++
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10f5783c6712852bfb53f457cea174f699c01ea0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="section"></a>section
Crée une section dans un fichier .obj.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## <a name="remarks"></a>Notes  
 La signification des termes du contrat *segment* et *section* sont interchangeables dans cette rubrique.  
  
 Une fois qu'une section est définie, elle reste valide pour le reste de la compilation. Toutefois, vous devez utiliser [__declspec (Allocate)](../cpp/allocate.md) ou rien ne sera placé dans la section.  
  
 *nom de la section* est un paramètre obligatoire qui sera le nom de la section. Ce nom ne doit pas être en conflit avec les noms de section standard. Consultez [/SECTION](../build/reference/section-specify-section-attributes.md) pour une liste de noms, vous ne devez pas utiliser lors de la création d’une section.  
  
 `attributes` est un paramètre optionnel qui se compose d'un ou plusieurs attributs séparés par des virgules que vous souhaitez assigner à la section. Les paramètres `attributes` possibles sont les suivants :  
  
 **read**  
 Permet les opérations de lecture sur les données.  
  
 **write**  
 Permet les opérations d'écriture sur les données.  
  
 **execute**  
 Permet d'exécuter le code.  
  
 **shared**  
 Partage la section entre tous les processus qui chargent l'image.  
  
 **nopage**  
 Marque la section comme non paginable ; utile pour les pilotes de périphériques Win32.  
  
 **nocache**  
 Marque la section comme ne pouvant pas être mise en cache ; utile pour les pilotes de périphériques Win32.  
  
 **discard**  
 Marque la section comme ne pouvant pas être supprimée ; utile pour les pilotes de périphériques Win32.  
  
 **remove**  
 Marque la section comme non résidents en mémoire ; pilotes de périphériques virtuels (V*x*D) uniquement.  
  
 Si vous ne spécifiez aucun attribut, la section aura des attributs en lecture et en écriture.  
  
## <a name="example"></a>Exemple  
 Dans l'exemple suivant, la première instruction identifie la section et ses attributs. L'entier `j` n'est pas placé dans `mysec` car il n'a pas été déclaré avec `__declspec(allocate)` ; `j` est placé dans la section de données. L'entier `i` n'est pas placé dans `mysec` en raison de son attribut de classe de stockage `__declspec(allocate)`.  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)