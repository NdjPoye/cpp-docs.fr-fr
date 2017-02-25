---
title: "CVSListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CVSListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVSListBox class"
  - "CVSListBox::PreTranslateMessage method"
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CVSListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CVSListBox` prend un contrôle de liste modifiable.  
  
## Syntaxe  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CVSListBox::CVSListBox](../Topic/CVSListBox::CVSListBox.md)|Construit un objet `CVSListBox`.|  
|`CVSListBox::~CVSListBox`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CVSListBox::AddItem](../Topic/CVSListBox::AddItem.md)|Ajoute une chaîne à un contrôle de liste.  \(Substitutions `CVSListBoxBase::AddItem`.\)|  
|[CVSListBox::EditItem](../Topic/CVSListBox::EditItem.md)|Commence une modification du texte d'un élément de contrôle liste.  \(Substitutions `CVSListBoxBase::EditItem`.\)|  
|[CVSListBox::GetCount](../Topic/CVSListBox::GetCount.md)|Récupère le nombre de chaînes dans un contrôle de liste modifiable.  \(Substitutions `CVSListBoxBase::GetCount`.\)|  
|[CVSListBox::GetItemData](../Topic/CVSListBox::GetItemData.md)|Récupère une valeur 32 bits spécifique à l'application associée à un élément modifiable de contrôle liste.  \(Substitutions `CVSListBoxBase::GetItemData`.\)|  
|[CVSListBox::GetItemText](../Topic/CVSListBox::GetItemText.md)|Extrait le texte d'un élément modifiable de contrôle liste.  \(Substitutions `CVSListBoxBase::GetItemText`.\)|  
|[CVSListBox::GetSelItem](../Topic/CVSListBox::GetSelItem.md)|Extrait l'index de base zéro actuel de l'élément sélectionné dans un contrôle de liste modifiable.  \(Substitutions `CVSListBoxBase::GetSelItem`.\)|  
|`CVSListBox::PreTranslateMessage`|Traduit des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows de [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et de [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  Pour plus de syntaxe d'informations et de méthode, consultez [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(Substitutions `CVSListBoxBase::PreTranslateMessage`.\)|  
|[CVSListBox::RemoveItem](../Topic/CVSListBox::RemoveItem.md)|Supprime un élément d'un contrôle de liste modifiable.  \(Substitutions `CVSListBoxBase::RemoveItem`.\)|  
|[CVSListBox::SelectItem](../Topic/CVSListBox::SelectItem.md)|Sélectionne une chaîne modifiable de contrôle liste.  \(Substitutions `CVSListBoxBase::SelectItem`.\)|  
|[CVSListBox::SetItemData](../Topic/CVSListBox::SetItemData.md)|Associe une valeur 32 bits spécifique à l'application avec un élément modifiable de contrôle liste.  \(Substitutions `CVSListBoxBase::SetItemData`.\)|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CVSListBox::GetListHwnd](../Topic/CVSListBox::GetListHwnd.md)|Retourne le handle au contrôle liste view incorporé par actuel.|  
  
## Notes  
 La classe d' `CVSListBox` fournit un jeu de boutons de modification qui permettent à l'utilisateur de créer, modifier, supprimer, ou réorganiser les éléments dans un contrôle de liste.  
  
 Voici une image du contrôle de liste modifiable.  La deuxième entrée de liste, intitulée « Item2 », est sélectionnée pour modifier.  
  
 ![Contrôle CVSListBox](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 Si vous utilisez l'éditeur de ressources pour ajouter un contrôle de liste modifiable, notez que le volet **Boîte à outils** de l'éditeur ne fournit pas un contrôle de liste modifiable intégré.  À la place, ajoutez un contrôle statique tel que le contrôle **Zone de groupe** .  l'infrastructure utilise le contrôle statique comme espace réservé pour spécifier la taille et la position du contrôle de liste modifiable.  
  
 Pour utiliser un contrôle de liste modifiable dans un modèle de boîte de dialogue, déclarez une variable d' `CVSListBox` dans votre classe de boîte de dialogue.  Pour prendre en charge l'échange de données entre la variable et le contrôle, définissez une macro entrée d' `DDX_Control` dans la méthode d' `DoDataExchange` de boîte de dialogue.  Par défaut, le contrôle de liste modifiable est créé sans boutons de modification.  Utilisez la méthode héritée de [CVSListBoxBase::SetStandardButtons](http://msdn.microsoft.com/fr-fr/129e530f-97e9-42eb-b128-371c2a5686ba) pour activer les boutons de modification.  
  
 Pour plus d'informations, consultez le dossier exemples, l'exemple d' `New Controls` , les fichiers de Page3.cpp et de Page3.h.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## Configuration requise  
 **en\-tête :** afxvslistbox.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)