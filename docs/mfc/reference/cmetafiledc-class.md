---
title: "CMetaFileDC Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMetaFileDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMetaFileDC class"
  - "métafichiers, implémenter"
  - "Windows metafiles [C++]"
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 23
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMetaFileDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un métafichier windows, qui contient une séquence de Graphics Device Interface \(GDI\) commande que vous pouvez relire pour créer une image souhaité ou au texte.  
  
## Syntaxe  
  
```  
class CMetaFileDC : public CDC  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMetaFileDC::CMetaFileDC](../Topic/CMetaFileDC::CMetaFileDC.md)|Construit un objet `CMetaFileDC`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMetaFileDC::Close](../Topic/CMetaFileDC::Close.md)|Ferme le contexte de périphérique et crée un handle de métafichier.|  
|[CMetaFileDC::CloseEnhanced](../Topic/CMetaFileDC::CloseEnhanced.md)|Ferme un contexte de périphérique de métafichier amélioré et crée un handle de métafichier amélioré.|  
|[CMetaFileDC::Create](../Topic/CMetaFileDC::Create.md)|Crée le contexte de périphérique de métafichier windows et l'attache à l'objet d' `CMetaFileDC` .|  
|[CMetaFileDC::CreateEnhanced](../Topic/CMetaFileDC::CreateEnhanced.md)|Crée un contexte de périphérique de métafichier pour un métafichier d'améliorer\-format.|  
  
## Notes  
 Pour implémenter un métafichier windows, créez d'abord un objet d' `CMetaFileDC` .  Appelez le constructeur d' `CMetaFileDC` , puis appelez la fonction membre de [Create](../Topic/CMetaFileDC::Create.md) , qui crée un contexte de périphérique de métafichier windows et l'attache à l'objet d' `CMetaFileDC` .  
  
 Envoyez ensuite l'objet d' `CMetaFileDC` que la séquence d' `CDC` GDI commande que vous avez l'intention d'elle de relire.  Seuls les commandes de GDI qui crée la sortie, telle qu' `MoveTo` et `LineTo`, peuvent être utilisées.  
  
 Après avoir envoyé les commandes souhaitées au métafichier, appelez la fonction membre de **Fermer** , qui ferme les contextes de périphérique de métafichier et retourne un handle de métafichier.  Possèdent l'objet d' `CMetaFileDC` .  
  
 [CDC::PlayMetaFile](../Topic/CDC::PlayMetaFile.md) peut ensuite utiliser le handle de métafichier pour lire le métafichier à plusieurs reprises.  Métafichier peut également être manipulé par les fonctions Windows telles que [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480), qui copie un métafichier sur le disque.  
  
 Lorsque le métafichier n'est plus nécessaire, supprimez \-le de la mémoire avec la fonction Windows de [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) .  
  
 Vous pouvez également implémenter l'objet d' `CMetaFileDC` afin qu'il puisse traiter des appels sortis attribut et des appels de GDI \(par exemple `GetTextExtent`.  Un tel métafichier est plus flexible et peut facilement réutiliser le code de GDI général, qui se compose souvent d'une combinaison de sortie et l'attribut appelle.  La classe d' `CMetaFileDC` hérite de deux contextes de périphérique, `m_hDC` et `m_hAttribDC`, d' `CDC`.  Le contexte de périphérique d' `m_hDC` gère tous les appels de sortie de [CDC](../../mfc/reference/cdc-class.md) GDI et les handles de contexte de périphérique d' `m_hAttribDC` tous les appels d'attribut d' `CDC` GDI.  Normalement, ces contextes de deux systèmes font référence au même périphérique.  Dans le cas de `CMetaFileDC`, le contrôleur de domaine d'attribut a la valeur **NULL** par défaut.  
  
 Créez un deuxième contexte de périphérique qui indique l'écran, une imprimante, ou le périphérique autre qu'un métafichier, puis appelez la fonction membre d' `SetAttribDC` pour associer le nouveau contexte de périphérique avec `m_hAttribDC`.  Les appels GDI des informations seront maintenant dirigés à nouveau `m_hAttribDC`.  Les appels GDI de sortie iront à `m_hDC`, qui représente le métafichier.  
  
 Pour plus d'informations sur `CMetaFileDC`, consultez [contextes de périphérique](../../mfc/device-contexts.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [CDC, classe](../../mfc/reference/cdc-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)