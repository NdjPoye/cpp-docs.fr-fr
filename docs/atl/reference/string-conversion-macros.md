---
title: "Macros de Conversion de chaîne | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
caps.latest.revision: 16
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
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: e322c3af297c288ec6c9ccdb1c04e58d0a5759ff
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="string-conversion-macros"></a>Macros de Conversion de chaînes
Ces macros fournissent des fonctionnalités de conversion de chaîne.  
  
 
##  <a name="atl_and_mfc_string_conversion_macros"></a>Macros de Conversion de chaînes MFC et ATL  
 Les macros de conversion de chaînes présentées ici sont valides à la fois pour ATL et pour MFC. Pour plus d’informations sur la conversion de chaînes MFC, consultez [TN059 : à l’aide de Macros de Conversion MBCS/Unicode MFC](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) et [MFC Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md).  
  
##  <a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE et Macros de Conversion de chaînes TEXTMETRIC  
 Ces macros créent une copie d’un [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) ou [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) structurer et convertir les chaînes dans la nouvelle structure en un nouveau type de chaîne. Les macros allocation de mémoire sur la pile pour la nouvelle structure et retournent un pointeur vers la nouvelle structure.  
  
```
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>Remarques  
 Exemple :  
  
 [!code-cpp[NVC_ATL_Utilities #128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
 et  
  
 [!code-cpp[NVC_ATL_Utilities #129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
 Les noms de macro, le type de chaîne dans la structure source se trouve sur la gauche (par exemple, **A**) et le type de chaîne dans la structure de destination se trouve à droite (par exemple, **W**). **A** stands for **LPSTR**, **OLE** stands for `LPOLESTR`, **T** stands for `LPTSTR`, and **W** stands for `LPWSTR`.  
  
 Par conséquent, `DEVMODEA2W` copies un `DEVMODE` structure avec **LPSTR** des chaînes dans un `DEVMODE` structure avec `LPWSTR` chaînes, `TEXTMETRICOLE2T` copies un `TEXTMETRIC` structure avec `LPOLESTR` des chaînes dans un `TEXTMETRIC` avec la structure `LPTSTR` chaînes et ainsi de suite.  
  
 Les deux chaînes converties dans le `DEVMODE` structure sont le nom du périphérique ( **dmDeviceName**) et le nom du formulaire ( **dmFormName**). Le `DEVMODE` macros de conversion de chaînes également mettre à jour de la taille de la structure ( **dmSize**).  
  
 Les quatre chaînes converties dans le `TEXTMETRIC` structure sont le premier caractère ( **tmFirstChar**), le dernier caractère ( **tmLastChar**), le caractère par défaut ( **tmDefaultChar**) et le caractère de saut ( **tmBreakChar**).  
  
 Le comportement de la `DEVMODE` et `TEXTMETRIC` macros de conversion de chaînes dépend de la directive de compilateur en vigueur, le cas échéant. Si les types source et de destination sont les mêmes, aucune conversion n'est effectuée. Modifier les directives de compilateur **T** et **OLE** comme suit :  
  
|Directive du compilateur appliquée|T devient|OLE devient|  
|----------------------------------|---------------|-----------------|  
|aucun|**A**|**W**|  
|**_UNICODE**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**_UNICODE** et **OLE2ANSI**|**W**|**A**|  
  
 Le tableau suivant répertorie les `DEVMODE` et `TEXTMETRIC` macros de conversion de chaîne.  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)


