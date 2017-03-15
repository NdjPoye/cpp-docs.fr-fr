---
title: "&lt;codecvt&gt;, énumérations | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 21162b7c25e09f2f77d2da1f4ee7797e68ec1e94
ms.lasthandoff: 02/24/2017

---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt;, énumérations
  
##  <a name="a-namecodecvtmodeenumerationa--codecvtmode-enumeration"></a><a name="codecvt_mode_enumeration"></a>  codecvt_mode, énumération  
 Spécifie des informations de configuration pour les facettes [locale](../standard-library/locale-class.md).  
  
```  
enum codecvt_mode {  
    consume_header = 4,  
    generate_header = 2,  
    little_endian = 1  
 };  
```  
  
### <a name="remarks"></a>Notes  
 L’énumération définit trois constantes qui fournissent des informations de configuration pour les facettes de paramètres régionaux déclarées dans [\<codecvt>](../standard-library/codecvt.md). Les différentes valeurs sont :  
  
- `consume_header`, pour consommer une séquence d’en-têtes initiale pendant la lecture d’une séquence multioctet et déterminer le mode Endian de la séquence multioctet suivante à lire  
  
- `generate_header`, pour générer une séquence d’en-têtes pendant l’écriture d’une séquence multioctet afin d’annoncer le mode Endian de la séquence multioctet suivante à écrire  
  
- `little_endian`, pour générer une séquence multioctet dans l’ordre du plus petit endian, par opposition à l’ordre par défaut du plus grand endian  
  
 Ces constantes peuvent être liées par une condition OR dans des combinaisons arbitraires.  
  
## <a name="see-also"></a>Voir aussi  
 [\<codecvt>](../standard-library/codecvt.md)


