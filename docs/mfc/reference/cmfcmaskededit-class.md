---
title: "CMFCMaskedEdit Class | Microsoft Docs"
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
  - "CMFCMaskedEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMaskedEdit class"
  - "CMFCMaskedEdit constructor"
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCMaskedEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCMaskedEdit` prend un contrôle d'édition masqué, qui valide les entrées d'utilisateur à un masque et affiche les résultats validées en fonction d'un modèle.  
  
## Syntaxe  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|Constructeur par défaut.|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCMaskedEdit::DisableMask](../Topic/CMFCMaskedEdit::DisableMask.md)|Désactive la validation des entrées d'utilisateur.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableGetMaskedCharsOnly.md)|Spécifie si la méthode d' `GetWindowText` récupère uniquement les caractères masqués.|  
|[CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md)|Initialise le contrôle d'édition masqué.|  
|[CMFCMaskedEdit::EnableSelectByGroup](../Topic/CMFCMaskedEdit::EnableSelectByGroup.md)|Spécifie si le contrôle d'édition masqué sélectionne les groupes particuliers d'entrée d'utilisateur, ou toute entrée utilisateur.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableSetMaskedCharsOnly.md)|Spécifie si le texte est validé par rapport à uniquement les caractères masqués, ou sur le masque entière.|  
|`CMFCMaskedEdit::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md)|Retrieves a validé le texte du contrôle d'édition masqué.|  
|[CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md)|Spécifie une chaîne de caractères valides que l'utilisateur peut entrer.|  
|[CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md)|Affiche une invite dans le contrôle d'édition masqué.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](../Topic/CMFCMaskedEdit::IsMaskedChar.md)|Appelé par l'infrastructure pour valider le caractère spécifié par rapport à le caractère correspondant de masque.|  
  
## Notes  
 Exécutez les étapes suivantes pour utiliser le contrôle d' `CMFCMaskedEdit` dans votre application :  
  
 1.  Incluez un objet d' `CMFCMaskedEdit` dans votre classe de fenêtre.  
  
 2.  Appelez la méthode d' [CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md) pour spécifier le masque.  
  
 3.  Appelez la méthode de [CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md) pour spécifier la liste de caractères valides.  
  
 4.  Appelez la méthode de [CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md) pour spécifier le texte par défaut pour le contrôle d'édition masqué.  
  
 5.  Appelez la méthode de [CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md) pour récupérer le texte validé.  
  
 Si vous n'appelez pas une ou plusieurs méthodes pour initialiser le masque, les caractères valides, et le texte par défaut, le contrôle d'édition masqué se comporte comme le contrôle d'édition standard se comporte.  
  
## Exemple  
 L'exemple suivant montre comment configurer un masque \(par exemple un numéro de téléphone\) à l'aide de la méthode d' `EnableMask` pour créer le masque pour le contrôle d'édition masqué, la méthode d' `SetValidChars` pour spécifier une chaîne de caractères valides que l'utilisateur peut entrer, et la méthode d' `SetWindowText` affiche une invite dans le contrôle d'édition masqué.  Cet exemple fait partie de [Nouvel exemples de contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/CPP/cmfcmaskededit-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/CPP/cmfcmaskededit-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## Configuration requise  
 **en\-tête :** afxmaskededit.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)