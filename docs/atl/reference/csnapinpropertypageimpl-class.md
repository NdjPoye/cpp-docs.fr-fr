---
title: Classe de CSnapInPropertyPageImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSnapInPropertyPageImpl
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f5db4d0742a423e9574db2a4268a9376491b2ed2
ms.lasthandoff: 02/24/2017

---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl (classe)
Cette classe fournit des méthodes pour implémenter un objet de page de propriétés de composant logiciel enfichable.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
CSnapInPropertyPageImpl : public CDialogImplBase
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Modifie le statut de la **OK** et **Annuler** boutons.|  
|[CSnapInPropertyPageImpl::Create](#create)|Initialise un nouvellement créé `CSnapInPropertyPageImpl` objet.|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Appelé par l’infrastructure lorsque l’utilisateur clique sur le **appliquer maintenant** bouton lors de l’utilisation d’une feuille de propriétés de type Assistant.|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Appelé par l’infrastructure lorsque l’utilisateur clique sur le **aide** bouton lors de l’utilisation d’une feuille de propriétés de type Assistant.|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Appelé par l’infrastructure lors de la page actuelle n’est plus active.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Appelé par l’infrastructure lorsque l’utilisateur clique sur le **Annuler** bouton et avant l’annulation a eu lieu.|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Appelé par l’infrastructure lorsque l’utilisateur clique sur le **réinitialiser** bouton lors de l’utilisation d’une feuille de propriétés de type Assistant.|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Appelé par l’infrastructure lorsque la page en cours devient active.|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Appelé par l’infrastructure lorsque l’utilisateur clique sur le **retour** bouton lors de l’utilisation d’une feuille de propriétés de type Assistant.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Appelé par l’infrastructure lorsque l’utilisateur clique sur le **Terminer** bouton lors de l’utilisation d’une feuille de propriétés de type Assistant.|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Appelé par l’infrastructure lorsque l’utilisateur clique sur le `Next` bouton lors de l’utilisation d’une feuille de propriétés de type Assistant.|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Transfère le message en cours pour toutes les pages de la feuille de propriétés.|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Appel à activer ou désactiver la **appliquer maintenant** bouton.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Les fenêtres **PROPSHEETPAGE** structure utilisée par le `CSnapInPropertyPageImpl` objet.|  
  
## <a name="remarks"></a>Remarques  
 `CSnapInPropertyPageImpl`Fournit une implémentation de base pour un objet de page de propriétés de composant logiciel enfichable. Les fonctionnalités de base d’une page de propriétés du composant logiciel enfichable sont implémentées à l’aide de plusieurs interfaces différentes et mappent les types.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsnap.h  
  
##  <a name="a-namecanceltoclosea--csnapinpropertypageimplcanceltoclose"></a><a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToClose  
 Appelez cette fonction après qu’une modification irrécupérable a été apportée aux données dans une page d’une feuille de propriétés modale.  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>Remarques  
 Cette fonction passe le **OK** bouton à **fermer** et désactiver la **Annuler** bouton. Modifier les alertes de l’utilisateur qu’une modification est permanente et les modifications ne peut pas être annulée.  
  
 Le `CancelToClose` fonction membre n’a aucun effet dans une feuille de propriétés non modale, car une feuille de propriétés non modale n’a pas une **Annuler** bouton par défaut.  
  
##  <a name="a-namecsnapinpropertypageimpla--csnapinpropertypageimplcsnapinpropertypageimpl"></a><a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 Construit un objet `CSnapInPropertyPageImpl`.  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTitle`  
 [in] Le titre de la page de propriétés.  
  
### <a name="remarks"></a>Remarques  
 Pour initialiser la structure sous-jacente, appelez [CSnapInPropertyPageImpl::Create](#create).  
  
##  <a name="a-namecreatea--csnapinpropertypageimplcreate"></a><a name="create"></a>CSnapInPropertyPageImpl::Create  
 Appelez cette fonction pour initialiser la structure sous-jacente de la page de propriétés.  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle vers un **PROPSHEETPAGE** structure qui contient les attributs de la feuille de propriété nouvellement créé.  
  
### <a name="remarks"></a>Remarques  
 Vous devez d’abord appeler [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) avant d’appeler cette fonction.  
  
##  <a name="a-namempspa--csnapinpropertypageimplmpsp"></a><a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp  
 `m_psp`est une structure dont les membres stockent les caractéristiques de **PROPSHEETPAGE**.  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>Notes  
 Utilisez cette structure pour initialiser l’apparence d’une page de propriétés après sa construction.  
  
 Pour plus d’informations sur cette structure, y compris une liste de ses membres, consultez la page [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonapplya--csnapinpropertypageimplonapply"></a><a name="onapply"></a>CSnapInPropertyPageImpl::OnApply  
 Cette fonction membre est appelée lorsque l’utilisateur clique sur le **OK** ou **appliquer maintenant** bouton.  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les modifications sont acceptées ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Avant de `OnApply` peut être appelée par l’infrastructure, vous devez appeler `SetModified` et affectez à son paramètre **TRUE**. Cela activera le **appliquer maintenant** bouton dès que l’utilisateur apporte une modification sur la page de propriétés.  
  
 Remplacez cette fonction membre pour spécifier l’action prise par votre programme lorsque l’utilisateur clique sur le **appliquer maintenant** bouton. Lors de la substitution, la fonction doit retourner **TRUE** pour accepter les modifications et **FALSE** pour empêcher la modification prenne effet.  
  
 L’implémentation par défaut de `OnApply` retourne **TRUE**.  
  
##  <a name="a-nameonhelpa--csnapinpropertypageimplonhelp"></a><a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp  
 Cette fonction membre est appelée lorsque l’utilisateur clique sur le **aide** bouton de la page de propriétés.  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction membre pour afficher l’aide de la page de propriétés.  
  
##  <a name="a-nameonkillactivea--csnapinpropertypageimplonkillactive"></a><a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive  
 Cette fonction membre est appelée lorsque la page n’est plus la page active.  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les données a été mis à jour avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction membre pour effectuer les tâches de validation de données spéciaux.  
  
##  <a name="a-nameonquerycancela--csnapinpropertypageimplonquerycancel"></a><a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnQueryCancel  
 Cette fonction membre est appelée lorsque l’utilisateur clique sur le **Annuler** bouton et avant l’annulation action a eu lieu.  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro pour permettre l’opération d’annulation ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction membre pour spécifier une action que le programme prend lorsque l’utilisateur clique sur le **Annuler** bouton.  
  
 L’implémentation par défaut de `OnQueryCancel` retourne **TRUE**.  
  
##  <a name="a-nameonreseta--csnapinpropertypageimplonreset"></a><a name="onreset"></a>CSnapInPropertyPageImpl::OnReset  
 Cette fonction membre est appelée lorsque l’utilisateur clique sur le **Annuler** bouton.  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>Remarques  
 Lorsque cette fonction est appelée, les modifications à toutes les pages de propriétés qui ont été apportées par l’utilisateur précédemment en cliquant sur les **appliquer maintenant** bouton sont ignorées, et la feuille de propriétés conserve le focus.  
  
 Remplacez cette fonction membre pour spécifier l’action prise par le programme lorsque l’utilisateur clique sur le **Annuler** bouton.  
  
##  <a name="a-nameonsetactivea--csnapinpropertypageimplonsetactive"></a><a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive  
 Cette fonction membre est appelée lorsque la page est choisie par l’utilisateur et devient la page active.  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la page a été définie correctement active ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction membre pour effectuer des tâches lorsqu’une page est activée. La substitution de cette fonction membre doit appeler la version par défaut avant tout autre traitement.  
  
 L’implémentation par défaut retourne **TRUE**.  
  
##  <a name="a-nameonwizardbacka--csnapinpropertypageimplonwizardback"></a><a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack  
 Cette fonction membre est appelée lorsque l’utilisateur clique sur le **dans** dans un Assistant.  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
-   0 pour passer automatiquement à la page précédente.  
  
-   -1 pour empêcher la modification de la page.  
  
 Pour accéder à une page différente de celle qui suit, retourner l’identificateur de la boîte de dialogue s’affiche.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction membre pour spécifier une action de l’utilisateur doit effectuer lorsque le **retour** bouton.  
  
##  <a name="a-nameonwizardfinisha--csnapinpropertypageimplonwizardfinish"></a><a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish  
 Cette fonction membre est appelée lorsque l’utilisateur clique sur le **Terminer** dans un Assistant.  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la feuille de propriétés est détruite à la fin de l’Assistant ; Sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction membre pour spécifier une action de l’utilisateur doit effectuer lorsque le **Terminer** du bouton.  
  
##  <a name="a-nameonwizardnexta--csnapinpropertypageimplonwizardnext"></a><a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext  
 Cette fonction membre est appelée lorsque l’utilisateur clique sur le `Next` dans un Assistant.  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
-   0 pour passer automatiquement à la page suivante.  
  
-   -1 pour empêcher la modification de la page.  
  
 Pour accéder à une page différente de celle qui suit, retourner l’identificateur de la boîte de dialogue s’affiche.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction membre pour spécifier une action de l’utilisateur doit effectuer lorsque le `Next` du bouton.  
  
##  <a name="a-namequerysiblingsa--csnapinpropertypageimplquerysiblings"></a><a name="querysiblings"></a>CSnapInPropertyPageImpl::QuerySiblings  
 Appelez cette fonction membre pour transférer un message à chaque page de la feuille de propriétés.  
  
```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `wParam`  
 [in] Spécifie des informations de message dépendant supplémentaires.  
  
 `lParam`  
 [in] Spécifie des informations de message dépendant supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le message ne doit pas être transféré à la page suivante de la propriété ; Sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Si une page retourne une valeur différente de zéro, la feuille de propriétés n’envoie pas de message pour les pages suivantes.  
  
##  <a name="a-namesetmodifieda--csnapinpropertypageimplsetmodified"></a><a name="setmodified"></a>CSnapInPropertyPageImpl::SetModified  
 Appelez cette fonction membre pour activer ou désactiver la **appliquer maintenant** bouton, selon si les paramètres dans la page de propriétés doivent être appliquées à l’objet externe approprié.  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bChanged`  
 [in] **TRUE** pour indiquer que les paramètres de page de propriété ont été modifiés depuis la dernière fois qu’ils ont été appliquées ; **FALSE** pour indiquer que les paramètres de page de propriété ont été appliquées, ou doivent être ignorées.  
  
### <a name="remarks"></a>Remarques  
 La feuille de propriétés conserve le suivi des pages sont « modifiées », autrement dit, les pages de propriétés pour lequel vous avez appelé **SetModified (TRUE)**. Le **appliquer maintenant** bouton sera toujours activé si vous appelez **SetModified (TRUE)** pour l’une des pages. Le **appliquer maintenant** bouton est désactivé lorsque vous appelez **SetModified (FALSE)** pour l’une des pages, mais uniquement si aucune des autres pages est « modifié ».  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

