---
title: "TN061&#160;: messages ON_NOTIFY et WM_NOTIFY | Microsoft Docs"
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
  - "ON_NOTIFY"
  - "WM_NOTIFY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages de notification"
  - "ON_NOTIFY (message)"
  - "ON_NOTIFY_EX (message)"
  - "ON_NOTIFY_EX_RANGE (message)"
  - "ON_NOTIFY_RANGE (message)"
  - "TN061"
  - "WM_NOTIFY (message)"
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN061&#160;: messages ON_NOTIFY et WM_NOTIFY
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette note technique fournit des informations générales sur le nouveau message de **WM\_NOTIFY** et décrit la méthode recommandée \(et la plus courante\) pour gérer les messages de **WM\_NOTIFY** de votre application MFC.  
  
 **Messages de notification dans Windows 3.x**  
  
 Dans Windows 3.x, les contrôles notifient leurs parents des événements tels que les clics de la souris, les modifications de contenu et lessélection, et contrôlent la peinture d'arrière\-plan en envoyant un message au parent.  De simples notifications sont envoyées comme des messages **WM\_COMMAND** spéciaux, avec le code de notification \(par exemple **BN\_CLICKED**\) et l'ID du contrôle compressés dans `wParam` et la poignée de contrôle dans `lParam`.  Notez que depuis que `wParam` et `lParam` sont complet, il n'y a aucun moyen de transmettre d'informations supplémentaires : ces messages ne peuvent qu'être de simples notifications.  Par exemple, dans les notifications de **BN\_CLICKED**, il est impossible d'envoyer des informations relatives à l'emplacement du curseur de la souris lorsque l'utilisateur a cliqué sur le bouton.  
  
 Lorsque les contrôles dans Windows 3.x doivent envoyer un message de notification qui contient des informations supplémentaires, elles utilisent un grand nombre de messages destinés à des usages spéciaux, y compris `WM_CTLCOLOR`, `WM_VSCROLL`, `WM_HSCROLL`, `WM_DRAWITEM`, `WM_MEASUREITEM`, `WM_COMPAREITEM`, `WM_DELETEITEM`, `WM_CHARTOITEM`, `WM_VKEYTOITEM`, et ainsi de suite.  Ces messages peuvent être répercutées sur le contrôle qui les a envoyés.  Pour plus d'informations, consultez [TN062 : Renvoi de message pour les contrôles Windows](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
 **Messages de notification dans Win32**  
  
 Pour les contrôles qui existaient dans Windows 3.1, l'API Win32 utilise la plupart des messages de notification utilisés dans les fenêtres 3.x.  Toutefois, Win32 ajoute également plusieurs contrôles complexes et sophistiqués à ceux pris en charge dans Windows 3.x.  Souvent, ces contrôles ont besoin d'envoyer des informations supplémentaires avec leurs messages de notification.  Au lieu d'ajouter un nouveau message de **WM\_\*** pour chaque nouvelle notification qui requiert des informations supplémentaires, les concepteurs de l'API Win32 ont choisi d'ajouter simplement un message, **WM\_NOTIFY**, qui peut passer n'importe quelle quantité d'informations supplémentaires de manière standardisée.  
  
 Les messages de**WM\_NOTIFY** contiennent l'ID du contrôle qui envoie le message dans `wParam` et un pointeur vers une structure dans `lParam`.  Cette structure est une structure **NMHDR** ou une plus grande structure qui a une structure de **NMHDR** comme premier membre.  Notez que puisque le membre de **NMHDR** est le premier, un pointeur vers la structure peut être utilisé comme pointeur vers **NMHDR** ou comme un pointeur vers une structure plus importante selon la façon dont vous le convertissez.  
  
 Dans la plupart des cas, le pointeur pointera sur une plus grande structure et vous devez le convertir lorsque vous utilisez.  Dans seulement quelques notifications, telles que les notifications communes \(dont le nom commence par **NM\_**\) et celles du contrôle d'info\-bulle **TTN\_SHOW** et **TTN\_POP**, sont une structure **NMHDR** vraiment utilisée.  
  
 La structure **NMHDR** ou le membre initial contient le descripteur et l'ID du contrôle qui envoie le message et le code de notification \(par exemple **TTN\_SHOW**\).  Le format de la structure de **NMHDR** est indiqué ci\-dessous :  
  
```  
typedef struct tagNMHDR {  
    HWND hwndFrom;  
    UINT idFrom;  
    UINT code;  
} NMHDR;  
```  
  
 Pour un message de **TTN\_SHOW**, le membre de **code** sera défini avec **TTN\_SHOW**.  
  
 La plupart des notifications passent un pointeur vers une plus grande structure qui contient une structure de **NMHDR** comme premier membre.  Par exemple, considérez la structure utilisée par le message de notification de **LVN\_KEYDOWN** du contrôle list VIEW, qui est envoyé lorsqu'une clé est enfoncée dans un contrôle list VIEW.  Les points de pointeur vers une structure de **LV\_KEYDOWN**, définie comme indiqué ci\-dessous :  
  
```  
typedef struct tagLV_KEYDOWN {  
    NMHDR hdr;     
    WORD wVKey;    
    UINT flags;    
} LV_KEYDOWN;  
```  
  
 Notez que puisque le membre de **NMHDR** est le premier dans cette structure, le pointeur que vous avez passé dans le message de notification peut être converti en un pointeur vers **NMHDR** ou un pointeur vers **LV\_KEYDOWN**.  
  
 **Notifications communes à tous les nouveaux contrôles Windows**  
  
 Certaines notifications sont communes à tous les nouveaux contrôles Windows.  Ces notifications passent un pointeur vers une structure de **NMHDR**.  
  
|Code de notification|Envoyé car|  
|--------------------------|----------------|  
|**NM\_CLICK**|L'utilisateur a cliqué sur le bouton de la souris dans le contrôle|  
|**NM\_DBLCLK**|L'utilisateur a double\-cliqué sur le bouton de la souris dans le contrôle|  
|**NM\_RCLICK**|L'utilisateur a cliqué sur le bouton droit de la souris dans le contrôle|  
|**NM\_RDBLCLK**|L'utilisateur a double\-cliqué sur le bouton droit de la souris dans le contrôle|  
|**NM\_RETURN**|L'utilisateur a appuyé sur la touche ENTRÉE lorsque le contrôle avait le focus d'entrée|  
|**NM\_SETFOCUS**|Le contrôle s'est vu offrir le focus d'entrée|  
|**NM\_KILLFOCUS**|Le contrôle a perdu le focus d'entrée|  
|**NM\_OUTOFMEMORY**|Le contrôle ne peut pas effectuer une opération car il n'y a pas assez de mémoire disponible|  
  
##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON\_NOTIFY : Messages de gestion WM\_NOTIFY dans les applications MFC  
 La fonction gère les messages de notification `CWnd::OnNotify`.  L'implémentation par défaut vérifie la table des messages à la recherche d'appels de gestionnaires de notifications.  En général vous ne remplacez pas `OnNotify`.  À la place, vous fournissez une fonction gestionnaire et ajoutez une entrée de la table des messages de ce gestionnaire à la table des messages de la classe de votre fenêtre propriétaire.  
  
 ClassWizard, via la feuille de propriétés de ClassWizard, peut créer des entrées de la table des messages `ON_NOTIFY` et vous fournir un squelette de fonction gestionnaire.  Pour plus d'informations sur la façon d'utiliser ClassWizard pour rendre cela plus facile, consultez [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md).  
  
 La macro table des messages `ON_NOTIFY` présente la syntaxe suivante :  
  
```  
  
ON_NOTIFY( wNotifyCode, id, memberFxn )  
```  
  
 par où les paramètres en italique sont remplacés :  
  
 `wNotifyCode`  
 Code du message de notification à gérer, par exemple **LVN\_KEYDOWN**.  
  
 `id`  
 Identificateur enfant du contrôle pour lequel la notification est envoyée.  
  
 `memberFxn`  
 La fonction membre à appeler lorsque cette notification est envoyée.  
  
 La fonction membre doit être déclarée avec le prototype suivant :  
  
```  
  
afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## Notes  
 où les paramètres en italique sont :  
  
 `pNotifyStruct`  
 Pointeur vers la structure de notification, comme décrit dans la section ci\-dessus.  
  
 *result*  
 Un pointeur vers le code résultat que vous pourrez définir avant de le retourner.  
  
## Exemple  
 Pour spécifier que désirez que la fonction membre `OnKeydownList1` traite les messages de **LVN\_KEYDOWN** de `CListCtrl` dont l'ID est `IDC_LIST1`, vous devez utiliser ClassWizard pour ajouter le code suivant à la table des messages :  
  
```  
ON_NOTIFY( LVN_KEYDOWN, IDC_LIST1, OnKeydownList1 )  
```  
  
 Dans l'exemple ci\-dessus, la fonction fournie par ClassWizard est :  
  
```  
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)  
{  
   LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;  
   // TODO: Add your control notification handler  
   //       code here  
  
   *pResult = 0;  
}  
```  
  
 Notez que ClassWizard fournit un pointeur du type approprié automatiquement.  Vous pouvez accéder à la structure de notification par `pNMHDR` ou `pLVKeyDow`.  
  
##  <a name="_mfcnotes_on_notify_range"></a> ON\_NOTIFY\_RANGE  
 Si vous devez traiter le même message de **WM\_NOTIFY** d'un ensemble de contrôles, vous pouvez utiliser **ON\_NOTIFY\_RANGE** plutôt que `ON_NOTIFY`.  Par exemple, vous pouvez demander un ensemble de boutons pour lesquels vous souhaitez exécuter la même action pour un message de notification particulier.  
  
 Lorsque vous utilisez **ON\_NOTIFY\_RANGE**, vous spécifiez une plage contiguës des identificateurs enfants pour lesquels traiter le message de notification en spécifiant les identificateurs enfants de début et de fin de la plage.  
  
 ClassWizard ne gère pas **ON\_NOTIFY\_RANGE**; pour l'utiliser, vous devez modifier votre table des messages vous\-même.  
  
 L'entrée de la table des messages et le prototype de la fonction pour **ON\_NOTIFY\_RANGE** sont les suivantes :  
  
```  
  
ON_NOTIFY_RANGE(   
wNotifyCode  
,   
id  
,   
idLast  
,   
memberFxn  
 )  
  
```  
  
 par où les paramètres en italique sont remplacés :  
  
 `wNotifyCode`  
 Code du message de notification à gérer, par exemple **LVN\_KEYDOWN**.  
  
 `id`  
 Le premier identificateur de la plage contiguës aux identificateurs.  
  
 `idLast`  
 Le dernier identificateur de la plage contiguës aux identificateurs.  
  
 `memberFxn`  
 La fonction membre à appeler lorsque cette notification est envoyée.  
  
 La fonction membre doit être déclarée avec le prototype suivant :  
  
```  
  
afx_msg void memberFxn( UINT id, NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## Notes  
 où les paramètres en italique sont :  
  
 `id`  
 L'identificateur enfant du contrôle qui envoie la notification.  
  
 `pNotifyStruct`  
 Pointeur vers la structure de notification, comme décrit ci\-dessus.  
  
 *result*  
 Un pointeur vers le code résultat que vous pourrez définir avant de le retourner.  
  
##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON\_NOTIFY\_EX, ON\_NOTIFY\_EX\_RANGE  
 Si vous souhaitez plusieurs objets dans le routage de notification pour traiter un message, vous pouvez utiliser **ON\_NOTIFY\_EX** \(ou **ON\_NOTIFY\_EX\_RANGE**\) plutôt que `ON_NOTIFY` \(ou **ON\_NOTIFY\_RANGE**\).  La seule différence entre la version **EX** et la version standard est que la fonction membre appelée pour la version **EX** retourne **BOOL** qui indique si le traitement des messages doit continuer.  Retourner **FALSE** vi cette fonction permet de traiter le même message dans plusieurs objets.  
  
 ClassWizard ne gère pas **ON\_NOTIFY\_EX** ou **ON\_NOTIFY\_EX\_RANGE** ; si vous souhaitez utiliser l'une de ces derniers, vous devez modifier votre table des messages vous\-même.  
  
 L'entrée de la table des messages et le prototype de la fonction pour **ON\_NOTIFY\_EX** et **ON\_NOTIFY\_EX\_RANGE** sont les suivantes.  Les significations des paramètres sont les mêmes que pour les versions non\-**EX**.  
  
```  
  
ON_NOTIFY_EX( nCode, id, memberFxn ) ON_NOTIFY_EX_RANGE( wNotifyCode, id, idLast, memberFxn )  
```  
  
 Le prototype pour les deux ce qui précède est identique :  
  
```  
  
afx_msg BOOL memberFxn( UINT id, NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## Notes  
 Dans les deux cas, `id` conserve l'identificateur enfant du contrôle qui envoie la notification.  
  
 La fonction doit retourner **TRUE** si le message de notification a été traité ou **FALSE** si d'autres objets du routage des commandes devraient avoir la possibilité de traiter le message.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)