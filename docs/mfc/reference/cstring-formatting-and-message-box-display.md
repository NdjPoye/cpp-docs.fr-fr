---
title: "Mise en forme de CString et affichage de la boîte de Message | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.strings
dev_langs:
- C++
helpviewer_keywords:
- CString objects, formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 48fc79f74bda10e43807d57fbcd7ed85fbb5d78b
ms.lasthandoff: 02/24/2017

---
# <a name="cstring-formatting-and-message-box-display"></a>Mise en forme de CString et affichage des boîtes de message
Un nombre de fonctions est fourni au format et analyser les `CString` objets. Vous pouvez utiliser ces fonctions chaque fois que vous devez manipuler `CString` objets, mais ils sont particulièrement utiles pour mettre en forme des chaînes qui apparaissent dans le texte de la boîte de message.  
  
 Ce groupe de fonctions inclut également une routine globale pour afficher une boîte de message.  
  
### <a name="cstring-functions"></a>Fonctions de CString  
  
|||  
|-|-|  
|[AfxExtractSubString](#afxextractsubstring)|Extraire des sous-chaînes séparés par un caractère unique à partir d’une chaîne source donné.|  
|[AfxFormatString1](#afxformatstring1)|Remplace une chaîne donnée pour les caractères de format « %1 » dans une chaîne contenue dans la table de chaînes.|  
|[AfxFormatString2](#afxformatstring2)|Chaînes de substitution deux pour le format de caractères « %1 » et « %2 » dans une chaîne contenue dans la table de chaînes.|  
|[AfxMessageBox](#afxmessagebox)|Affiche une boîte de message.|  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxwin.h  
  
##  <a name="a-nameafxextractsubstringa--afxextractsubstring"></a><a name="afxextractsubstring"></a>AfxExtractSubString  
 Cette fonction globale peut être utilisée pour extraire une sous-chaîne d’une chaîne source donné.  
  
```   
BOOL AFXAPI AfxExtractSubString (
    CString& rString,  
    LPCTSTR lpszFullString,  
    int iSubString,  
    TCHAR chSep  = '\n'); 
```  
  
### <a name="parameters"></a>Paramètres  
 *rString*  
 -   Référence à un [CString](../../atl-mfc-shared/using-cstring.md) objet qui reçoit une sous-chaîne individuelle.  
  
 *lpszFullString*  
 -   Chaîne contenant le texte complet de la chaîne à extraire.  
  
 *iSubString*  
 -   Index de base zéro de la sous-chaîne à extraire *lpszFullString*.  
  
 *chSep*  
 -   Caractère de séparation utilisé pour délimiter les sous-chaînes.  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si la fonction extrait la sous-chaîne à l’index fourni ; sinon, **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utile pour extraire plusieurs sous-chaînes d’une chaîne source lorsqu’un caractère unique connu sépare chaque sous-chaîne. Cette fonction recherche à partir du début de la `lpszFullString` paramètre chaque fois qu’elle est appelée.  
  
 Cette fonction retourne FALSE si le paramètre `lpszFullString` a **NULL** ou la fonction atteint la fin de `lpszFullString` sans recherche `iSubString`+&1; des occurrences du caractère séparateur spécifié. Le `rString` paramètre ne sera pas modifié à partir de sa valeur d’origine si `lpszFullString` a **NULL**; sinon, le `rString` paramètre est défini sur une chaîne vide si la sous-chaîne n’a pas pu être extrait de l’index spécifié.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities&#48;](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxwin.h  
  
##  <a name="a-nameafxformatstring1a--afxformatstring1"></a><a name="afxformatstring1"></a>AfxFormatString1  
 Remplace la chaîne pointée par `lpsz1` pour toutes les instances des caractères « %1 » dans la ressource de chaîne de modèle identifié par `nIDS`.  
  
```  
void  AfxFormatString1(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1); 
```  
  
### <a name="parameters"></a>Paramètres  
 `rString`  
 Une référence à un `CString` objet qui contient la chaîne résultante après la substitution est effectuée.  
  
 `nIDS`  
 L’ID de ressource de la chaîne de modèle sur lequel la substitution sera effectuée.  
  
 `lpsz1`  
 Chaîne qui remplace le format de caractères « %1 » dans la chaîne de modèle.  
  
### <a name="remarks"></a>Notes  
 La nouvelle chaîne est stockée dans `rString`. Par exemple, si la chaîne de la table de chaînes est « Fichier %1 introuvable », et `lpsz1` est égal à « C:\MYFILE. TXT », puis `rString` contient la chaîne « fichier C:\MYFILE. TXT introuvable ». Cette fonction est utile pour mettre en forme les chaînes envoyées à des boîtes de message et d’autres fenêtres.  
  
 Si les caractères de format « %1 » apparaissant plusieurs fois dans la chaîne, plusieurs substitutions sont effectuées.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities&#25;](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxwin.h  
  
##  <a name="a-nameafxformatstring2a--afxformatstring2"></a><a name="afxformatstring2"></a>AfxFormatString2  
 Remplace la chaîne pointée par `lpsz1` pour toutes les instances des caractères « %1 » et la chaîne pointée par `lpsz2` pour toutes les instances des caractères « %2 », de la ressource de chaîne de modèle identifié par `nIDS`.  
  
```   
void AfxFormatString2(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1,  
    LPCTSTR lpsz2); 
```  
  
### <a name="parameters"></a>Paramètres  
 `rString`  
 Une référence à la `CString` qui contient la chaîne résultante après la substitution est effectuée.  
  
 `nIDS`  
 La chaîne ID de la chaîne de modèle sur lequel la substitution sera effectuée.  
  
 `lpsz1`  
 Chaîne qui remplace le format de caractères « %1 » dans la chaîne de modèle.  
  
 `lpsz2`  
 Chaîne qui remplace le format de caractères « %2 » dans la chaîne de modèle.  
  
### <a name="remarks"></a>Remarques  
 La nouvelle chaîne est stockée dans `rString`. Par exemple, si la chaîne de la table de chaînes est « Fichier %1 est introuvable dans le répertoire %2 », `lpsz1` pointe vers « MYFILE. « TXT » et `lpsz2` pointe vers « C:\MYDIR », puis `rString` contient la chaîne « fichier MYFILE. TXT introuvable dans le répertoire C:\MYDIR »  
  
 Si le format de caractères « %1 » ou « %2 » apparaître plusieurs fois dans la chaîne, plusieurs substitutions sont effectuées. Qu’ils aient à être dans l’ordre numérique.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities&#26;](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxwin.h  
  
##  <a name="a-nameafxmessageboxa--afxmessagebox"></a><a name="afxmessagebox"></a>AfxMessageBox  
 Affiche une boîte de message à l’écran.  
  
```  
int AfxMessageBox(
    LPCTSTR lpszText,  
    UINT nType = MB_OK,  
    UINT nIDHelp = 0);

int AFXAPI AfxMessageBox(
    UINT nIDPrompt,  
    UINT nType = MB_OK,  
    UINT nIDHelp = (UINT) -1); 
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszText`  
 Pointe vers une `CString` objet ou chaîne terminée par le caractère null qui contient le message à afficher dans la boîte de message.  
  
 `nType`  
 Style de la boîte de message. Appliquer de la [styles de zone de message](../../mfc/reference/message-box-styles.md) à la zone.  
  
 `nIDHelp`  
 L’ID de contexte d’aide pour le message. 0 indique que le contexte d’aide de l’application par défaut sera utilisé.  
  
 `nIDPrompt`  
 Un ID unique utilisé pour faire référence à une chaîne dans la table.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro s’il y a pas suffisamment de mémoire pour afficher la boîte de message ; Sinon, une des valeurs suivantes est retournée :  
  
- **IDABORT** abandonner l’a été sélectionné.  
  
- **IDCANCEL** bouton Annuler l’a été sélectionné.  
  
- **IDIGNORE** bouton Ignorer l’a été sélectionné.  
  
- **IDNO** N° le bouton a été sélectionné.  
  
- **IDOK** OK le bouton a été sélectionné.  
  
- **IDRETRY** bouton Réessayer l’a été sélectionné.  
  
- **IDYES** Oui le bouton a été sélectionné.  
  
 Si une boîte de message contient un bouton Annuler, le **IDCANCEL** valeur est renvoyée si la touche ÉCHAP est enfoncée ou si le bouton Annuler est sélectionné. Si la boîte de message ne possède aucun bouton Annuler, en appuyant sur la touche ÉCHAP n’a aucun effet.  
  
 Les fonctions [AfxFormatString1](#afxformatstring1) et [AfxFormatString2](#afxformatstring2) peut être utile pour la mise en forme du texte qui apparaît dans une boîte de message.  
  
### <a name="remarks"></a>Remarques  
 Le premier formulaire de cette surcharge fonction affiche une chaîne de texte vers laquelle pointe `lpszText` de la boîte de message et `nIDHelp` pour décrire un contexte d’aide. Le contexte d’aide est utilisé pour accéder à une rubrique d’aide associée lorsque l’utilisateur appuie sur la touche d’aide (F1 généralement).  
  
 La deuxième forme de la fonction utilise la ressource de chaîne avec l’ID `nIDPrompt` pour afficher un message dans la boîte de message. La page d’aide associée se trouve à la valeur de `nIDHelp`. Si la valeur par défaut `nIDHelp` est utilisé (â € 1 »), l’ID de ressource de chaîne, `nIDPrompt`, est utilisé pour le contexte d’aide. Pour plus d’informations sur la définition des contextes d’aide, consultez [technique Remarque 28](../../mfc/tn028-context-sensitive-help-support.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#133;](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CStringT (classe)](../../atl-mfc-shared/reference/cstringt-class.md)

