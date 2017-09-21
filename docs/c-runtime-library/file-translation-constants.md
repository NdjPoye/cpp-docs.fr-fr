---
title: Constantes de traduction de fichiers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.constants.file
dev_langs:
- C++
helpviewer_keywords:
- translation constants
- file translation [C++], constants
- translation, file translation constants
- translation, constants
- constants [C++], file translation mode
- file translation [C++]
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
caps.latest.revision: 6
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
ms.openlocfilehash: e3005ebe8d36f77a470634b9fdd0003d9b6bb8d5
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="file-translation-constants"></a>Constantes de translation de fichier
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Remarques  
 Ces constantes spécifient le mode de translation (**« b »** ou **« t »**). Le mode est inclus dans la chaîne qui spécifie le type d'accès (**"r"**, **"w"**, **"a"**, **"r+"**, **"w+"**, **"a+"**).  
  
 Les modes de translation sont les suivants :  
  
 **t**  
 Ouvre en mode texte (traduit). Dans ce mode, les combinaisons retour chariot-saut de ligne sont traduites en flux d'une ligne (saut de ligne) en entrée, et les caractères de saut de ligne sont traduits en combinaisons retour chariot/saut de en sortie. De même, Ctrl+Z est interprété comme un caractère de fin de fichier en entrée. Dans les fichiers ouverts en lecture ou lecture/écriture, `fopen` recherche un Ctrl+Z à la fin du fichier et le supprime, si possible. En effet, l’utilisation des fonctions `fseek` et `ftell` pour se déplacer dans un fichier qui se termine par un Ctrl+Z peut provoquer un comportement incorrect de `fseek` vers la fin du fichier.  
  
> [!NOTE]
>  L’option **t** ne fait pas partie de la norme ANSI pour `fopen` et `freopen`. Il s’agit d’une extension Microsoft qui ne doit pas être utilisée là où la portabilité ANSI est souhaitée.  
  
 **b**  
 Ouvre en mode binaire (non traduit). Les traductions ci-dessus sont supprimées.  
  
 Si **t** ou **b** n'est pas spécifié dans *mode*, le mode de traduction est défini par la variable de mode par défaut [_fmode](../c-runtime-library/fmode.md). Pour plus d’informations sur l’utilisation des modes texte et binaire, consultez [E/S de fichier en mode texte et binaire](../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## <a name="see-also"></a>Voir aussi  
 [_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)