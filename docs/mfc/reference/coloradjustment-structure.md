---
title: "Structure de réglage des couleurs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COLORADJUSTMENT
dev_langs:
- C++
helpviewer_keywords:
- COLORADJUSTMENT structure
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7f88877fa009abf4e811ba0a99b7e0e1683f998a
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT, structure
Le `COLORADJUSTMENT` structure définit les valeurs d’ajustement de couleur utilisés par Windows `StretchBlt` et **StretchDIBits** fonctions lors de la `StretchBlt` mode est **demi-teintes**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct  tagCOLORADJUSTMENT {    /* ca */  
    WORD caSize;  
    WORD caFlags;  
    WORD caIlluminantIndex;  
    WORD caRedGamma;  
    WORD caGreenGamma;  
    WORD caBlueGamma;  
    WORD caReferenceBlack;  
    WORD caReferenceWhite;  
    SHORT caContrast;  
    SHORT caBrightness;  
    SHORT caColorfulness;  
    SHORT caRedGreenTint;  
} COLORADJUSTMENT;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *caSize*  
 Spécifie la taille de la structure en octets.  
  
 *caFlags*  
 Spécifie comment l’image de sortie doit être préparée. Ce membre peut être défini sur **NULL** ou n’importe quelle combinaison des valeurs suivantes :  
  
- **CA_NEGATIVE** indique que la valeur négative de l’image d’origine doit être affichée.  
  
- **CA_LOG_FILTER** Spécifie qu’une fonction logarithmique doit être appliquée à la densité des couleurs de sortie finale. Cela augmentera le contraste des couleurs lorsque la luminance est faible.  
  
 *caIlluminantIndex*  
 Spécifie la luminance de la source lumineuse sous lequel l’objet d’image est affichée. Ce membre peut être défini à une des valeurs suivantes :  
  
- **ILLUMINANT_EQUAL_ENERGY**  
  
- **ILLUMINANT_A**  
  
- **ILLUMINANT_B**  
  
- **ILLUMINANT_C**  
  
- **ILLUMINANT_D50**  
  
- **ILLUMINANT_D55**  
  
- **ILLUMINANT_D65**  
  
- **ILLUMINANT_D75**  
  
- **ILLUMINANT_F2**  
  
- **ILLUMINANT_TURNGSTEN**  
  
- **ILLUMINANT_DAYLIGHT**  
  
- **ILLUMINANT_FLUORESCENT**  
  
- **ILLUMINANT_NTSC**  
  
 *caRedGamma*  
 Spécifie la valeur de correction gamma de puissance n de rouge principal des couleurs source. La valeur doit être comprise entre 2 500 à 65,000. Une valeur de 10 000 ne signifie aucune correction gamma.  
  
 *caGreenGamma*  
 Spécifie la valeur de correction gamma de puissance n de vert principal des couleurs source. La valeur doit être comprise entre 2 500 à 65,000. Une valeur de 10 000 ne signifie aucune correction gamma.  
  
 *caBlueGamma*  
 Spécifie la valeur de correction gamma de puissance n de bleu primaire des couleurs source. La valeur doit être comprise entre 2 500 à 65,000. Une valeur de 10 000 ne signifie aucune correction gamma.  
  
 *caReferenceBlack*  
 Spécifie la référence noire pour les couleurs de la source. Les couleurs plus sombres que ce sont traités en noir. La valeur doit être dans la plage de 0 à 4 000.  
  
 *caReferenceWhite*  
 Spécifie la référence de blanche pour les couleurs de la source. Les couleurs plus claires que ce sont traités comme blanc. La valeur doit être comprise entre 6 000 à 10 000.  
  
 *caContrast*  
 Spécifie la quantité de contraste à appliquer à l’objet source. La valeur doit être comprise entre -100 et 100. La valeur 0 ne signifie aucun ajustement de contraste.  
  
 *caBrightness*  
 Spécifie la quantité de luminosité à appliquer à l’objet source. La valeur doit être comprise entre -100 et 100. La valeur 0 ne signifie aucun ajustement de la luminosité.  
  
 *caColorfulness*  
 Spécifie la quantité de colorfulness à appliquer à l’objet source. La valeur doit être comprise entre -100 et 100. La valeur 0 ne signifie aucun ajustement colorfulness.  
  
 *caRedGreenTint*  
 Spécifie la quantité d’ajustement rouge ou vert à appliquer à l’objet source. La valeur doit être comprise entre -100 et 100. Nombres positifs ajusterait vers le rouge et ajustez les nombres négatifs vers le vert. 0 ne signifie aucun ajustement de la teinte.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)



