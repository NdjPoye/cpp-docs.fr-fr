---
title: "Limitations CImage avec les syst&#232;mes d&#39;exploitation ant&#233;rieurs | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImage (classe), limitations"
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Limitations CImage avec les syst&#232;mes d&#39;exploitation ant&#233;rieurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

De nombreuses fonctions `CImage` fonctionnent uniquement avec les versions plus récentes de Windows : Windows 95\/98 ou Windows NT 4.0, ou Windows 2000.  Cet article décrit les limitations de version de certaines méthodes.  
  
 [CImage::PlgBlt](../Topic/CImage::PlgBlt.md) et [CImage::MaskBlt](../Topic/CImage::MaskBlt.md) fonctionnent uniquement avec Windows NT 4.0 ou version ultérieure.  Ils ne fonctionneront pas avec les applications exécutées sur Windows 95\/98 ou version ultérieure.  
  
 [CImage::AlphaBlend](../Topic/CImage::AlphaBlend.md) et [CImage::TransparentBlt](../Topic/CImage::TransparentBlt.md) fonctionnent uniquement avec Windows 2000 ou version ultérieure et Windows 98 ou version ultérieure car vous devez lier avec msimg32.lib pour utiliser ces méthodes. \(Cette bibliothèque est disponible uniquement pour les applications de Windows 2000 ou version ultérieure et Windows 98 ou ultérieure.\)  
  
 Vous pouvez inclure `AlphaBlend` et `TransparentBlt` dans une application qui s'exécute sur Windows 95 ou Windows NT 4.0 uniquement si elles ne sont jamais appelées.  Si votre application comporte ces méthodes, et doit s'exécuter sur des systèmes d'exploitation antérieurs, vous devez utiliser [\/delayload](../build/reference/delayload-delay-load-import.md) de l'éditeur de liens pour différer le chargement de msimg32.lib.  Tant que votre application n'appelle pas une de ces méthodes lors de son exécution sous Windows NT 4.0 ou Windows 95, elle n'essaie pas de charger msimg32.lib.  Vous pouvez vérifier si la prise en charge de transparence est disponible à l'aide de la méthode `CImage::IsTransparencySupported`.  
  
## Exemple  
 [!code-cpp[NVC_MFCDocViewSDI#8](../mfc/codesnippet/CPP/cimage-limitations-with-earlier-operating-systems_1.cpp)]  
  
 Pour compiler une application qui appelle ces méthodes, insérez une instruction de \#define \_WIN32\_WINNT avant \#including tous les en\-têtes système, indiquant que la version de Windows est égale ou supérieure à 5.0 :  
  
 [!code-cpp[NVC_MFCDocViewSDI#9](../mfc/codesnippet/CPP/cimage-limitations-with-earlier-operating-systems_2.h)]  
  
 Si votre application n'a pas besoin de s'exécuter sur un système d'exploitation plus ancien que Windows 2000 ou Windows 98, vous pouvez lier directement à msimg32.lib sans utiliser **\/delayload**.  
  
 [CImage::Draw](../Topic/CImage::Draw.md) se comporte différemment en cas d'utilisation avec Windows 2000 et Windows 98 qu'avec Windows NT 4.0 ou Windows 95.  
  
 Si vous compilez votre application avec \_WIN32\_WINNT défini à une valeur inférieure à 0x0500, **Draw** fonctionne, mais ne gère pas la transparence automatiquement sur les systèmes exécutant Windows 2000 et Windows 98 et versions ultérieures.  
  
 Si vous compilez votre application avec \_WIN32\_WINNT défini à 0x0500 ou supérieur, **Draw** gère la transparence automatiquement sur des systèmes de Windows 2000 ou Windows 98 et versions ultérieures.  La procédure fonctionne en outre, sans prise en charge de transparence, avec Windows NT 4.0 et Windows 95 ; toutefois, vous devez utiliser **\/delayload** pour différer le chargement de msimg32.LIB, comme décrit ci\-dessus pour `AlphaBlend` et `TransparentBlt`.  
  
## Voir aussi  
 [CImage Class](../atl-mfc-shared/reference/cimage-class.md)