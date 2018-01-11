---
title: "Limitations de CImage avec les systèmes d’exploitation antérieurs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CImage
dev_langs: C++
helpviewer_keywords: CImage class [MFC], limitations
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27046704975bf8f5e28f12acbfa72e860660fdbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cimage-limitations-with-earlier-operating-systems"></a>Limitations CImage avec les systèmes d'exploitation antérieurs
De nombreuses fonctions `CImage` fonctionnent uniquement avec les versions plus récentes de Windows : Windows 95/98 ou Windows NT 4.0, ou Windows 2000. Cet article décrit les limitations de version de certaines méthodes.  
  
 [CImage::PlgBlt](../atl-mfc-shared/reference/cimage-class.md#plgblt) et [CImage::MaskBlt](../atl-mfc-shared/reference/cimage-class.md#maskblt) fonctionnent avec Windows NT 4.0 ou version ultérieure. Ces éléments ne fonctionnent pas avec les applications exécutées sous Windows 95/98 ou version ultérieure.  
  
 [CImage::AlphaBlend](../atl-mfc-shared/reference/cimage-class.md#alphablend) et [CImage::TransparentBlt](../atl-mfc-shared/reference/cimage-class.md#transparentblt) fonctionnent avec uniquement Windows 2000 ou version ultérieure et Windows 98 ou version ultérieure, car vous devez lier avec msimg32.lib pour utiliser ces méthodes. (Cette bibliothèque est disponible uniquement pour les applications de Windows 2000 ou version ultérieure et Windows 98 ou ultérieure.)  
  
 Vous pouvez inclure `AlphaBlend` et `TransparentBlt` dans une application qui s'exécute sous Windows 95 ou Windows NT 4.0 uniquement si elles ne sont jamais appelées. Si votre application inclut ces méthodes, et il doit s’exécuter sur les systèmes d’exploitation antérieurs, vous devez utiliser l’éditeur de liens [DELAYLOAD](../build/reference/delayload-delay-load-import.md) pour différer le chargement de msimg32.lib. Tant que votre application n'appelle pas une de ces méthodes lors de son exécution sous Windows NT 4.0 ou Windows 95, elle n'essaiera pas de charger msimg32.lib. Vous pouvez vérifier si la prise en charge de transparence est disponible à l'aide de la méthode `CImage::IsTransparencySupported`.  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocViewSDI#8](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_1.cpp)]  
  
 Pour compiler une application qui appelle ces méthodes, insérez une instruction #define _WIN32_WINNT avant #including pour tous les en-têtes système, indiquant que la version de Windows est égale ou supérieure à 5.0 :  
  
 [!code-cpp[NVC_MFCDocViewSDI#9](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_2.h)]  
  
 Si votre application n’a pas besoin pour s’exécuter sur un système d’exploitation antérieurs à Windows 2000 ou Windows 98, vous pouvez lier directement à msimg32.lib sans utiliser de **DELAYLOAD**.  
  
 [CImage::Draw](../atl-mfc-shared/reference/cimage-class.md#draw) se comporte différemment lorsqu’il est utilisé avec Windows 2000 et Windows 98 qu’avec Windows NT 4.0 ou Windows 95.  
  
 Si vous compilez votre application avec _WIN32_WINNT définie à une valeur inférieure à 0 x 0500, **dessiner** sera travail, mais il ne gère pas la transparence automatiquement sur les systèmes exécutant Windows 2000 et Windows 98 et versions ultérieures.  
  
 Si vous compilez votre application avec _WIN32_WINNT définie à 0 x 0500 ou supérieure, **dessiner** gère la transparence automatiquement sur les systèmes exécutant Windows 2000 ou Windows 98 et versions ultérieures. Il fonctionne également, mais sans prise en charge de transparence, avec Windows NT 4.0 et Windows 95 ; Toutefois, vous devez utiliser **DELAYLOAD** pour différer le chargement de msimg32. LIB, comme décrit ci-dessus pour `AlphaBlend` et `TransparentBlt`.  
  
## <a name="see-also"></a>Voir aussi  
 [CImage, classe](../atl-mfc-shared/reference/cimage-class.md)
