---
title: "CBitmapButton Class | Microsoft Docs"
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
  - "CBitmapButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bitmaps, button controls"
  - "boutons, bitmap"
  - "CBitmapButton class"
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBitmapButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée des contrôles de bouton poussoir étiquetés avec des images générées une correspondance de bits au lieu du texte.  
  
## Syntaxe  
  
```  
class CBitmapButton : public CButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CBitmapButton::CBitmapButton](../Topic/CBitmapButton::CBitmapButton.md)|Construit un objet `CBitmapButton`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CBitmapButton::AutoLoad](../Topic/CBitmapButton::AutoLoad.md)|Associe un bouton dans une boîte de dialogue avec un objet de la classe d' `CBitmapButton` , charge les bitmaps de noms, classes et le bouton pour adapter la bitmap.|  
|[CBitmapButton::LoadBitmaps](../Topic/CBitmapButton::LoadBitmaps.md)|Initialise l'objet en chargeant un ou plusieurs ressources bitmap nommées du fichier de ressources de l'application et en liant les bitmaps à l'objet.|  
|[CBitmapButton::SizeToContent](../Topic/CBitmapButton::SizeToContent.md)|Classe le bouton pour s'adapter à la bitmap.|  
  
## Notes  
 Les objets d'`CBitmapButton` contiennent jusqu'à quatre bitmap, qui contiennent des images pour les différents états qu'un bouton peut en supposant que : en haut de \(ou normale\), vers le bas \(ou sélectionné\), le focus, et désactivé.  Seule la première bitmap est requise ; les autres sont facultatifs.  
  
 Les images de bouton bitmap incluent la bordure autour de l'image ainsi que de l'image elle\-même.  La bordure lit généralement un rôle en affichant l'état du bouton.  Par exemple, la bitmap pour l'état ayant le focus est généralement à celui de l'état supérieur mais avec une incrustation à tiret rectangle de la bordure ou une ligne pleine épaisse sur la bordure.  La bitmap de l'état désactivé généralement ressemble à celui du rapport haut mais a le contraste inférieur \(comme une sélection de menu estompée ou grisée\).  
  
 Ces images peuvent être de toute taille, mais tous sont traités comme s'ils étaient la même taille qu'un bitmap pour l'état haut.  
  
 Les différentes applications requièrent différentes combinaisons des images bitmap :  
  
|Haut|Bas|Focused|Disabled|Application|  
|----------|---------|-------------|--------------|-----------------|  
|×||||Bitmap|  
|×|×|||Bouton sans style de **WS\_TABSTOP**|  
|×|×|×|×|Bouton de dialogue avec tous les rapports|  
|×|×|×||Bouton de dialogue avec le style de **WS\_TABSTOP**|  
  
 En créant un contrôle bouton bitmap, définissez le style de **BS\_OWNERDRAW** pour spécifier que le bouton est owner\-drawn.  Cela fait envoyer des fenêtres les messages d' `WM_MEASUREITEM` et d' `WM_DRAWITEM` du bouton ; l'infrastructure gère ces messages et gère l'apparence du bouton pour vous.  
  
### Pour créer un contrôle bouton bitmap dans la zone cliente d'une fenêtre  
  
1.  Créez un à quatre images bitmap pour le bouton.  
  
2.  Construisez l'objet de [CBitmapButton](../Topic/CBitmapButton::CBitmapButton.md) .  
  
3.  Appelez la fonction de création pour créer le contrôle bouton windows et le lier à l'objet d' `CBitmapButton` .  
  
4.  Appelez la fonction membre de [LoadBitmaps](../Topic/CBitmapButton::LoadBitmaps.md) pour charger les ressources bitmap une fois le bouton bitmap est construit.  
  
### Pour inclure un contrôle bouton bitmap dans une boîte de dialogue  
  
1.  Créez un à quatre images bitmap pour le bouton.  
  
2.  Créez un modèle de boîte de dialogue avec un bouton owner\-draw positionnée où le bouton bitmap.  La taille du bouton dans le modèle n'importe pas.  
  
3.  Définissez la légende du bouton une valeur telle que « **MYIMAGE** » et définissez un symbole du bouton comme **IDC\_MYIMAGE**.  
  
4.  Dans le script de ressources de votre application, donnez chacune des images créées pour le bouton un ID construit en ajoutant une des lettres U « , » D « , » F « , » ou « X » \(pour, vers le bas, le focus, et désactivé\) à la chaîne utilisée pour la légende de bouton dans l'étape 3.  Pour la légende « **MYIMAGE**de bouton, » par exemple, les identificateurs seraient**MYIMAGEU**« , »**MYIMAGED**, »**MYIMAGEF**, » et « **MYIMAGEX** ». Vous **must** spécifiez l'ID de vos bitmap entre guillemets.  Sinon l'éditeur de ressources assignera un entier à la ressource et MFC échoue lors de le chargement de l'image.  
  
5.  Dans la classe de boîte de dialogue de votre application \(dérivée d' `CDialog`\), ajoutez un objet membre d' `CBitmapButton` .  
  
6.  Dans la routine d' [OnInitDialog](../Topic/CDialog::OnInitDialog.md) de l'objet d' `CDialog` , appelez la fonction de [Charge automatique](../Topic/CBitmapButton::AutoLoad.md) de l'objet d' `CBitmapButton` , en utilisant comme paramètres l'ID du contrôle du bouton et le pointeur de **this** de l'objet d' `CDialog` .  
  
 Si vous souhaitez gérer des messages de notification de windows, tels que **BN\_CLICKED**, envoyé par un contrôle bouton bitmap à son parent \(généralement une classe dérivée de **CDialog\)**, ajoutez à `CDialog`objet dérivé une entrée de la table des messages et une fonction membre gestionnaire de messages pour chaque message.  Les notifications envoyées par un objet d' `CBitmapButton` sont les mêmes que celles envoyées par un objet de [CButton](../../mfc/reference/cbutton-class.md) .  
  
 La classe [CToolBar](../../mfc/reference/ctoolbar-class.md) adopte une approche différente des boutons bitmap.  
  
 Pour plus d'informations sur `CBitmapButton`, consultez[contrôles](../../mfc/controls-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [Exemple CTRLTEST MFC](../../top/visual-cpp-samples.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)