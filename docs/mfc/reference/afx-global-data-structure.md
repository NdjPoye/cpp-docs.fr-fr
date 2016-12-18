---
title: "AFX_GLOBAL_DATA, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GLOBAL_DATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_GLOBAL_DATA (structure)"
  - "AFX_GLOBAL_DATA (constructeur)"
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
caps.latest.revision: 30
caps.handback.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AFX_GLOBAL_DATA, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `AFX_GLOBAL_DATA` contient des champs et des méthodes qui permettent de gérer l’infrastructure ou de personnaliser l’apparence et le comportement de votre application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct AFX_GLOBAL_DATA  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Construit une structure `AFX_GLOBAL_DATA` .|  
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::CleanUp](#afx_global_data__cleanup)|Libère les ressources allouées par l’infrastructure, telles que les pinceaux, les polices et les DLL.|  
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#afx_global_data__d2d1makerotatematrix)|Crée une transformation de rotation qui pivote autour d’un point spécifié selon un angle spécifié.|  
|[AFX_GLOBAL_DATA::DrawParentBackground](#afx_global_data__drawparentbackground)|Dessine l’arrière-plan du parent d’un contrôle dans la zone spécifiée.|  
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#afx_global_data__drawtextonglass)|Dessine le texte spécifié dans le style visuel du thème spécifié.|  
|[AFX_GLOBAL_DATA::ExcludeTag](#afx_global_data__excludetag)|Supprime la paire de balises XML spécifiée dans une mémoire tampon spécifiée.|  
|[AFX_GLOBAL_DATA::GetColor](#afx_global_data__getcolor)|Récupère la couleur actuelle de l’élément d’interface utilisateur spécifié.|  
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#afx_global_data__getdirect2dfactory)|Renvoie un pointeur à l’interface `ID2D1Factory` qui est stockée dans les données globales. Si l’interface n’est pas initialisée, elle est créée avec les paramètres par défaut.|  
|[AFX_GLOBAL_DATA::GetHandCursor](#afx_global_data__gethandcursor)|Récupère le curseur prédéfini qui a la forme d’une main et dont l’identificateur est `IDC_HAND`.|  
|[AFX_GLOBAL_DATA::GetITaskbarList](#afx_global_data__getitaskbarlist)|Crée et stocke dans les données globales un pointeur vers l’interface ITaskBarList.|  
|[AFX_GLOBAL_DATA::GetITaskbarList3](#afx_global_data__getitaskbarlist3)|Crée et stocke dans les données globales un pointeur vers l’interface ITaskBarList3.|  
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#afx_global_data__getnonclientmetrics)|Récupère les mesures associées à la zone non cliente des fenêtres non réduites.|  
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#afx_global_data__getshellautohidebars)|Détermine les positions des barres de masquage automatique de l’interpréteur de commandes.|  
|[AFX_GLOBAL_DATA::GetTextHeight](#afx_global_data__gettextheight)|Récupère la hauteur des caractères de texte dans la police actuelle.|  
|[AFX_GLOBAL_DATA::GetWICFactory](#afx_global_data__getwicfactory)|Renvoie un pointeur à l’interface `IWICImagingFactory` qui est stockée dans les données globales. Si l’interface n’est pas initialisée, elle est créée avec les paramètres par défaut.|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#afx_global_data__getwritefactory)|Renvoie un pointeur à l’interface `IDWriteFactory` qui est stockée dans les données globales. Si l’interface n’est pas initialisée, elle est créée avec les paramètres par défaut.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|Initialise les fabriques `D2D`, `DirectWrite`et `WIC` . Appelez cette méthode avant que la fenêtre principale soit initialisée.|  
|[AFX_GLOBAL_DATA::Is32BitIcons](#afx_global_data__is32biticons)|Indique si les icônes 32 bits prédéfinies sont prises en charge.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|Détermine si `D2D` a été initialisé.|  
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#afx_global_data__isdwmcompositionenabled)|Fournit un moyen simple d’appeler la méthode Windows [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) .|  
|[AFX_GLOBAL_DATA::IsHighContrastMode](#afx_global_data__ishighcontrastmode)|Indique si les images sont actuellement affichées avec un contraste élevé.|  
|[AFX_GLOBAL_DATA::OnSettingChange](#afx_global_data__onsettingchange)|Détecte l’état actuel des fonctionnalités de masquage automatique de la barre des tâches et de l’animation des menus du Bureau.|  
|[AFX_GLOBAL_DATA::RegisterWindowClass](#afx_global_data__registerwindowclass)|Inscrit la classe de fenêtre MFC spécifiée.|  
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#afx_global_data__releasetaskbarrefs)|Libère les interfaces obtenues par les méthodes GetITaskbarList et GetITaskbarList3.|  
|[AFX_GLOBAL_DATA::Resume](#afx_global_data__resume)|Réinitialise les pointeurs de fonction internes qui accèdent à des méthodes prenant en charge [les thèmes et les styles visuels](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)Windows.|  
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#afx_global_data__setlayeredattrib)|Fournit un moyen simple d’appeler la méthode Windows [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) .|  
|[AFX_GLOBAL_DATA::SetMenuFont](#afx_global_data__setmenufont)|Crée la police logique spécifiée.|  
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#afx_global_data__shellcreateitemfromparsingname)|Crée et initialise un objet élément d’interpréteur de commandes à partir d’un nom de l’analyse.|  
|[AFX_GLOBAL_DATA::UpdateFonts](#afx_global_data__updatefonts)|Réinitialise les polices logiques qui sont utilisées par l’infrastructure.|  
|[AFX_GLOBAL_DATA::UpdateSysColors](#afx_global_data__updatesyscolors)|Initialise les couleurs, la profondeur de couleur, les pinceaux, les stylets et les images qui sont utilisés par l’infrastructure.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#afx_global_data__enableaccessibilitysupport)|Active ou désactive la prise en charge de Microsoft Active Accessibility. Active Accessibility fournit des méthodes fiables pour exposer des informations sur les éléments d’interface utilisateur.|  
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__isaccessibilitysupport)|Indique si la prise en charge de Microsoft Active Accessibility est activée.|  
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#afx_global_data__iswindowslayersupportavailable)|Indique si le système d’exploitation prend en charge les fenêtres superposées.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#afx_global_data__bisosalphablendingsupport)|Indique si le système d’exploitation actuel prend en charge la simulation de transparence.|  
|[AFX_GLOBAL_DATA::bIsWindows7](#afx_global_data__biswindows7)|Indique si l’application est exécutée sur le système d’exploitation Windows 7 ou ultérieur|  
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#afx_global_data__clractivecaptiongradient)|Spécifie la couleur de dégradé de la légende active. Généralement utilisé pour les volets d’ancrage.|  
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#afx_global_data__clrinactivecaptiongradient)|Spécifie la couleur de dégradé de la légende inactive. Généralement utilisé pour les volets d’ancrage.|  
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#afx_global_data__m_busebuiltin32biticons)|Indique si l’infrastructure utilise des icônes de couleur 32 bits prédéfinies ou des icônes d’une résolution inférieure.|  
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#afx_global_data__m_busesystemfont)|Indique si une police système est utilisée pour les menus, les barres d’outils et les rubans.|  
|[AFX_GLOBAL_DATA::m_hcurHand](#afx_global_data__m_hcurhand)|Stocke le handle du curseur en forme de main.|  
|[AFX_GLOBAL_DATA::m_hcurStretch](#afx_global_data__m_hcurstretch)|Stocke le handle du curseur d’étirement horizontal.|  
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#afx_global_data__m_hcurstretchvert)|Stocke le handle du curseur d’étirement vertical.|  
|[AFX_GLOBAL_DATA::m_hiconTool](#afx_global_data__m_hicontool)|Stocke le handle de l’icône d’outil.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#afx_global_data__m_nautohidetoolbarmargin)|Spécifie le décalage entre la barre d’outils de masquage automatique la plus à gauche et le côté gauche de la barre d’ancrage.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#afx_global_data__m_nautohidetoolbarspacing)|Spécifie l’intervalle entre les barres d’outils de masquage automatique.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#afx_global_data__m_ndragframethicknessdock)|Spécifie l’épaisseur du cadre de glissement qui est utilisé pour communiquer l’état d’ancrage.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#afx_global_data__m_ndragframethicknessfloat)|Spécifie l’épaisseur du cadre de glissement qui est utilisé pour communiquer l’état flottant.|  
  
## <a name="remarks"></a>Notes  
 La plupart des données dans la structure `AFX_GLOBAL_DATA` sont initialisées au démarrage de votre application.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxglobals.h  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


## <a name="a-nameafxglobaldatabisosalphablendingsupporta-afxglobaldatabisosalphablendingsupport"></a><a name="afx_global_data__bisosalphablendingsupport"></a> AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
Indique si le système d’exploitation prend en charge la fusion alpha.  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
## <a name="remarks"></a>Notes  
 `TRUE` Indique la fusion alpha est pris en charge ; dans le cas contraire, `FALSE`.  
  

## <a name="a-nameafxglobaldatacleanupa-afxglobaldatacleanup"></a><a name="afx_global_data__cleanup"></a> AFX_GLOBAL_DATA::CleanUp
Libère les ressources allouées par l’infrastructure, telles que les pinceaux, les polices et les DLL.  
  
  
```  
void CleanUp();
```  
## <a name="a-nameafxglobaldatad2d1makerotatematrixa-afxglobaldatad2d1makerotatematrix"></a><a name="afx_global_data__d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
Crée une transformation de rotation qui pivote autour d’un point spécifié selon un angle spécifié.  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
#### <a name="parameters"></a>Paramètres  
 `angle`  
 L’angle de rotation vers la droite, en degrés.  
  
 `center`  
 Le point autour duquel pivoter.  
  
 `matrix`  
 Lorsque cette méthode est retournée, contient la nouvelle transformation de rotation. Vous devez allouer le stockage pour ce paramètre.  
  
## <a name="return-value"></a>Valeur de retour  
 Sinon, retourne S_OK en cas de réussite, ou une valeur d’erreur.  
  
## <a name="a-nameafxglobaldatadrawparentbackgrounda-afxglobaldatadrawparentbackground"></a><a name="afx_global_data__drawparentbackground"></a> AFX_GLOBAL_DATA::DrawParentBackground
Dessine l’arrière-plan du parent d’un contrôle dans la zone spécifiée.  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `pWnd`  
 Pointeur vers la fenêtre d’un contrôle.  
  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `lpRect`  
 Pointeur vers un rectangle qui délimite la zone à dessiner. La valeur par défaut est `NULL`.  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si cette méthode a réussi ; dans le cas contraire, `FALSE`.  
  
## <a name="a-nameafxglobaldatadrawtextonglassa-afxglobaldatadrawtextonglass"></a><a name="afx_global_data__drawtextonglass"></a> AFX_GLOBAL_DATA::DrawTextOnGlass
Dessine le texte spécifié dans le style visuel du thème spécifié.  
  
  
```  
BOOL DrawTextOnGlass(
    HTHEME hTheme,   
    CDC* pDC,   
    int iPartId,   
    int iStateId,   
    CString strText,   
    CRect rect,   
    DWORD dwFlags,   
    int nGlowSize = 0,   
    COLORREF clrText = (COLORREF)-1);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `hTheme`  
 Handle vers les données de thème d’une fenêtre ou `NULL`. Si ce paramètre n’est pas `NULL` et que les thèmes sont pris en charge, l’infrastructure utilise le thème spécifié pour dessiner le texte. Sinon, l’infrastructure n’utilise pas de thème pour dessiner le texte.  
  
 Utilisez la méthode [OpenThemeData](http://msdn.microsoft.com/library/windows/desktop/bb759821) pour créer un `HTHEME`.  
  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `iPartId`  
 Composant du contrôle ayant l’apparence de texte désirée. Pour plus d’informations, consultez la colonne Composants de la table figurant dans [Composants et états](http://msdn.microsoft.com/library/windows/desktop/bb773210). Si cette valeur est égale à 0, le texte est dessiné avec la police par défaut ou une police sélectionnée dans le contexte de l’appareil.  
  
 [in] `iStateId`  
 État du contrôle ayant l’apparence de texte désirée. Pour plus d’informations, consultez la colonne États de la table figurant dans [Composants et états](http://msdn.microsoft.com/library/windows/desktop/bb773210).  
  
 [in] `strText`  
 Texte à dessiner.  
  
 [in] `rect`  
 Limite de la zone dans laquelle le texte spécifié est dessiné.  
  
 [in] `dwFlags`  
 Combinaison de bits (OR) d’indicateurs qui spécifient comment le texte spécifié est dessiné.  
  
 Si le `hTheme` paramètre est `NULL` ou si les thèmes ne sont pas pris en charge et activés, le `nFormat` paramètre de la [CDC::DrawText](../../mfc/reference/cdc-class.md#cdc__drawtext) méthode décrit les indicateurs valides. Si les thèmes sont pris en charge, le paramètre `dwFlags` de la méthode [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) décrit les indicateurs valides.  
  
 [in] `nGlowSize`  
 Taille d’un éclat dessiné à l’arrière-plan avant de dessiner le texte spécifié. La valeur par défaut est 0.  
  
 [in] `clrText`  
 Couleur utilisée pour dessiner le texte spécifié. La valeur par défaut est la couleur par défaut.  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si un thème est utilisé pour dessiner le texte spécifié ; dans le cas contraire, `FALSE`.  
  
## <a name="remarks"></a>Notes  
 Un thème définit le style visuel d’une application. Un thème n’est pas utilisé pour dessiner le texte si le paramètre `hTheme` a la valeur `NULL`, si la méthode [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) n’est pas prise en charge, ou encore si la composition du [Gestionnaire de fenêtrage](http://msdn.microsoft.com/library/windows/desktop/aa969540) est désactivée.  
  
 
## <a name="see-also"></a>Voir aussi  
 [AFX_GLOBAL_DATA (Structure)](../../mfc/reference/afx-global-data-structure.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [Composants et États](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC::DrawText](../../mfc/reference/cdc-class.md#cdc__drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [Gestionnaire de fenêtres du bureau](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Activer et contrôler la Composition DWM](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataenableaccessibilitysupporta-afxglobaldataenableaccessibilitysupport"></a><a name="afx_global_data__enableaccessibilitysupport"></a> AFX_GLOBAL_DATA::EnableAccessibilitySupport
Active ou désactive la prise en charge de Microsoft Active Accessibility.  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 `TRUE` Pour activer la prise en charge d’accessibilité ; `FALSE` pour désactiver la prise en charge d’accessibilité. La valeur par défaut est `TRUE`.  
  
## <a name="remarks"></a>Notes  
 Active Accessibility est une technologie COM qui améliore les façon dont les programmes et le système d’exploitation de Windows fonctionne avec les produits de technologie d’assistance. Il fournit des méthodes fiables pour exposer des informations sur les éléments d’interface utilisateur. Toutefois, un modèle d’accessibilité plus récent appelé Microsoft UI Automation est maintenant disponible. Pour une comparaison des deux technologies, consultez [UI Automation et Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md).  
  
 Utilisez le [AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__IsAccessibilitySupport.md) méthode pour déterminer si la prise en charge de Microsoft Active Accessibility est activée.  
  
 
## <a name="see-also"></a>Voir aussi  
 [UI Automation et Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)   
 [AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__IsAccessibilitySupport.md)

## <a name="a-nameafxglobaldataexcludetaga-afxglobaldataexcludetag"></a><a name="afx_global_data__excludetag"></a> AFX_GLOBAL_DATA::ExcludeTag
Supprime la paire de balises XML spécifiée dans une mémoire tampon spécifiée.  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `strBuffer`  
 Une mémoire tampon de texte.  
  
 [in] `lpszTag`  
 Le nom d’une paire d’ouverture et de fermeture des balises XML.  
  
 [out] `strTag`  
 Lorsque cette méthode est retournée, la `strTag` paramètre contient le texte entre les balises XML balises sont nommés par le `lpszTag` paramètre. Les espaces de début ou de fin sont tronqué à partir du résultat.  
  
 [in] `bIsCharsList`  
 `TRUE` Pour convertir les symboles pour les caractères d’échappement dans la `strTag` paramètre en caractères d’échappement réelle : `FALSE` ne pas à effectuer la conversion. La valeur par défaut est `FALSE`. Pour plus d'informations, consultez la section Notes.  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si cette méthode a réussi ; dans le cas contraire, `FALSE`.  
  
## <a name="remarks"></a>Notes  
 Une paire de balises XML se compose de nommé des balises qui indiquent le début et la fin d’une séquence de texte dans la mémoire tampon spécifiée. Le `strBuffer` paramètre spécifie la mémoire tampon et le `lpszTag` paramètre spécifie le nom des balises XML.  
  
 Utilisez les symboles dans le tableau suivant pour encoder un jeu de caractères d’échappement dans la mémoire tampon spécifiée. Spécifiez `TRUE` pour la `bIsCharsList` paramètre pour convertir les symboles dans le `strTag` paramètre en caractères d’échappement réelle. Le tableau suivant utilise le [_T()](../../c-runtime-library/data-type-mappings.md) macro pour spécifier les symboles et les chaînes de caractères d’échappement.  
  
|Symbole|Caractère d'échappement|  
|------------|----------------------|  
|_T("\\\t")|_T("\t")|  
|_T("\\\n")|_T("\n")|  
|_T("\\\r")|_T("\r")|  
|_T("\\\b")|_T("\b")|  
|_T("LT")|_T("\<")|  
|_T("GT")|_T(">")|  
|_T("AMP")|_T("&")|  
  
## <a name="a-nameafxglobaldatagetcolora-afxglobaldatagetcolor"></a><a name="afx_global_data__getcolor"></a> AFX_GLOBAL_DATA::GetColor
Récupère la couleur actuelle de l’élément d’interface utilisateur spécifié.  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `nColor`  
 Une valeur qui spécifie un élément d’interface utilisateur dont la couleur est récupérée. Pour obtenir la liste des valeurs valides, consultez la `nIndex` paramètre de la [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) méthode.  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur de couleur RVB de l’élément d’interface utilisateur spécifié. Pour plus d'informations, consultez la section Notes.  
  
## <a name="remarks"></a>Notes  
 Si le `nColor` paramètre est hors limites, la valeur de retour est zéro. Zéro est également une valeur RVB, vous ne pouvez pas utiliser cette méthode pour déterminer si une couleur système est pris en charge par le système d’exploitation actuel. Utilisez plutôt le [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) méthode, qui renvoie `NULL` Si la couleur n’est pas prise en charge.  
  
## <a name="see-also"></a>Voir aussi  

 [GetSysColor (fonction)](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="a-nameafxglobaldatagetdirect2dfactorya-afxglobaldatagetdirect2dfactory"></a><a name="afx_global_data__getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory
 Retourne un pointeur vers l’interface ID2D1Factory stockée dans les données globales. Si l’interface n’est pas initialisée, elle est créée avec les paramètres par défaut.  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’interface ID2D1Factory si la création d’une fabrique réussit, ou NULL si la création échoue ou système d’exploitation actuel ne prend pas prise en charge D2D.  
  
AFX_GLOBAL_DATA::GetHandCursor récupère le curseur prédéfini qui ressemble à une main et dont l’identificateur est `IDC_HAND`.  
  
  
```  
HCURSOR GetHandCursor();
```  
  
## <a name="return-value"></a>Valeur de retour  
 Le handle du curseur main.  

## <a name="a-nameafxglobaldatagetnonclientmetricsa-afxglobaldatagetnonclientmetrics"></a><a name="afx_global_data__getnonclientmetrics"></a> AFX_GLOBAL_DATA::GetNonClientMetrics
Récupère les mesures associées à la zone non cliente des fenêtres non réduites.  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in, out] `info`  
 A [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) structure qui contient les mesures évolutives associés à la zone non cliente d’une fenêtre non réduite.  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si cette méthode réussit ; dans le cas contraire, `FALSE`.  
 
  
## <a name="see-also"></a>Voir aussi   
 [Structure NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="a-nameafxglobaldatagettextheighta-afxglobaldatagettextheight"></a><a name="afx_global_data__gettextheight"></a> AFX_GLOBAL_DATA::GetTextHeight
 Récupère la hauteur des caractères de texte dans la police actuelle.  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `bHorz`  
 `TRUE` pour récupérer la hauteur des caractères lorsque le texte à l’horizontale ; `FALSE` pour récupérer la hauteur des caractères lorsque le texte verticalement. La valeur par défaut est `TRUE`.  
  
## <a name="return-value"></a>Valeur de retour  
 La hauteur de la police actuelle, qui est mesurée à partir de son ascendante à son hampe inférieure.  
  
## <a name="a-nameafxglobaldatagetwicfactorya-afxglobaldatagetwicfactory"></a><a name="afx_global_data__getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory
Retourne un pointeur vers l’interface IWICImagingFactory stockée dans les données globales. Si l’interface n’est pas initialisée, elle est créée avec les paramètres par défaut.  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur interface IWICImagingFactory si la création d’une fabrique réussit, ou NULL si la création échoue ou système d’exploitation actuel ne prend pas en charge WIC.  
  
## <a name="a-nameafxglobaldatagetwritefactorya-afxglobaldatagetwritefactory"></a><a name="afx_global_data__getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory
Retourne un pointeur vers l’interface IDWriteFactory stockée dans les données globales. Si l’interface n’est pas initialisée, elle est créée avec les paramètres par défaut.  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur interface IDWriteFactory si la création d’une fabrique réussit, ou NULL si la création échoue ou système d’exploitation actuel ne prend pas en charge DirectWrite.  
 
## <a name="a-nameafxglobaldatainitd2da-afxglobaldatainitd2d"></a><a name="afx_global_data__initd2d"></a> AFX_GLOBAL_DATA::InitD2D
Initialise les fabriques D2D, DirectWrite et WIC. Appelez cette méthode avant que la fenêtre principale soit initialisée.  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
#### <a name="parameters"></a>Paramètres  
 `d2dFactoryType`  
 Le modèle de thread de la fabrique D2D et des ressources qu’il crée.  
  
 `writeFactoryType`  
 Une valeur qui indique si l’objet de fabrique d’écriture sera être partagé ou isolé  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si les fabriques ont été initialisées, FAUX - dans le cas contraire  
  
## <a name="a-nameafxglobaldatais32biticonsa-afxglobaldatais32biticons"></a><a name="afx_global_data__is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons
Indique si les icônes 32 bits prédéfinies sont prises en charge.  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si des icônes de 32 bits prédéfinies sont prises en charge ; dans le cas contraire, `FALSE`.  
  
## <a name="remarks"></a>Notes  
 Cette méthode retourne `TRUE` Si le framework prend en charge les icônes intégrés 32 bits et si le système d’exploitation prend en charge 16 bits par pixel ou plus, et si les images ne sont pas affichées avec un contraste élevé.  
  
## <a name="a-nameafxglobaldataisaccessibilitysupporta-afxglobaldataisaccessibilitysupport"></a><a name="afx_global_data__isaccessibilitysupport"></a> AFX_GLOBAL_DATA::IsAccessibilitySupport
Indique si la prise en charge de Microsoft Active Accessibility est activée.  
  
  
```  
BOOL IsAccessibilitySupport() const;

 
```  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si la prise en charge de l’accessibilité est activée ; dans le cas contraire, `FALSE`.  
  
## <a name="remarks"></a>Notes  
 Microsoft Active Accessibility était la solution précédemment pour rendre les applications accessibles. Microsoft UI Automation est le nouveau modèle d’accessibilité pour Microsoft Windows et est destinée à répondre aux besoins des produits de technologie d’assistance et outils de test automatisés. Pour plus d’informations, consultez [UI Automation et Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md).  
  
 Utilisez le [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#afx_global_data__EnableAccessibilitySupport.md) méthode pour activer ou désactiver la prise en charge d’Active Accessibility.  
  

## <a name="see-also"></a>Voir aussi  
 [UI Automation et Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)

## <a name="a-nameafxglobaldataisd2dinitializeda-afxglobaldataisd2dinitialized"></a><a name="afx_global_data__isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized
 Détermine si le D2D a été initialisé.  
  
  
```  
BOOL IsD2DInitialized() const;

 
```  
  
## <a name="return-value"></a>Valeur de retour  
 TRUE si D2D a été initialisé ; Sinon, FALSE.  
  
## <a name="a-nameafxglobaldataisdwmcompositionenableda-afxglobaldataisdwmcompositionenabled"></a><a name="afx_global_data__isdwmcompositionenabled"></a> AFX_GLOBAL_DATA::IsDwmCompositionEnabled
Fournit un moyen simple d’appeler la méthode Windows [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) .  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si [Gestionnaire de fenêtrage](http://msdn.microsoft.com/library/windows/desktop/aa969540) la composition (DWM) est activée ; sinon, `FALSE`.  
  
## <a name="see-also"></a>Voir aussi    
 [Gestionnaire de fenêtres du bureau](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Activer et contrôler la Composition DWM](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataishighcontrastmodea-afxglobaldataishighcontrastmode"></a><a name="afx_global_data__ishighcontrastmode"></a> AFX_GLOBAL_DATA::IsHighContrastMode
 Indique si les images sont actuellement affichées avec un contraste élevé.    
```  
BOOL IsHighContrastMode() const;

 
```  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si les images sont affichées actuellement en mode de contraste élevé noir ou blanc. dans le cas contraire, `FALSE`.  
  
## <a name="remarks"></a>Notes  
 En mode de contraste élevé noir, face à la lumière des bords sont blanches et l’arrière-plan est noir. En mode de contraste élevé blanche, face à la lumière des bords sont noirs et l’arrière-plan est blanc.  
  
## <a name="a-nameafxglobaldataiswindowslayersupportavailablea-afxglobaldataiswindowslayersupportavailable"></a><a name="afx_global_data__iswindowslayersupportavailable"></a> AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
Indique si le système d’exploitation prend en charge les fenêtres superposées.  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const;

 
```  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si les fenêtres superposées sont pris en charge ; dans le cas contraire, `FALSE`.  
  
## <a name="remarks"></a>Notes  
 Prise en charge des fenêtres superposées, *ancrage actifs* marqueurs d’utilisent des fenêtres superposées.  
  
## <a name="a-nameafxglobaldatambusebuiltin32biticonsa-afxglobaldatambusebuiltin32biticons"></a><a name="afx_global_data__m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
Indique si l’infrastructure utilise des icônes de couleur 32 bits prédéfinies ou des icônes d’une résolution inférieure.  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
## <a name="remarks"></a>Notes  
 `TRUE` Spécifie que le framework utilise des icônes de couleur 32 bits ; `FALSE` Spécifie les icônes de résolution inférieur. Le `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` constructeur initialise ce membre en `TRUE`.  
  
 Ce membre doit être défini au démarrage de l’application.  
  
## <a name="a-nameafxglobaldatambusesystemfonta-afxglobaldatambusesystemfont"></a><a name="afx_global_data__m_busesystemfont"></a> AFX_GLOBAL_DATA::m_bUseSystemFont
Indique si une police système est utilisée pour les menus, les barres d’outils et les rubans.  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
## <a name="remarks"></a>Notes  
 `TRUE` Spécifie l’utilisation d’une police système ; dans le cas contraire, `FALSE`. Le `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` constructeur initialise ce membre en `FALSE`.  
  
 Test de ce membre n’est pas le seul moyen pour l’infrastructure déterminer la police à utiliser. Le `AFX_GLOBAL_DATA::UpdateFonts` méthode teste également les polices par défaut et de remplacement pour déterminer les styles visuels sont disponibles à appliquer aux menus, barres d’outils et les rubans.  
  
## <a name="a-nameafxglobaldatamhcurhanda-afxglobaldatamhcurhand"></a><a name="afx_global_data__m_hcurhand"></a> AFX_GLOBAL_DATA::m_hcurHand
Stocke le handle du curseur en forme de main.  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="a-nameafxglobaldatamhcurstretcha-afxglobaldatamhcurstretch"></a><a name="afx_global_data__m_hcurstretch"></a> AFX_GLOBAL_DATA::m_hcurStretch
Stocke le handle du curseur d’étirement horizontal.  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="a-nameafxglobaldatamhcurstretchverta-afxglobaldatamhcurstretchvert"></a><a name="afx_global_data__m_hcurstretchvert"></a> AFX_GLOBAL_DATA::m_hcurStretchVert
Stocke le handle du curseur d’étirement vertical.  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="a-nameafxglobaldatamhicontoola-afxglobaldatamhicontool"></a><a name="afx_global_data__m_hicontool"></a> AFX_GLOBAL_DATA::m_hiconTool
Stocke le handle de l’icône d’outil.  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="a-nameafxglobaldatamnautohidetoolbarmargina-afxglobaldatamnautohidetoolbarmargin"></a><a name="afx_global_data__m_nautohidetoolbarmargin"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
Spécifie l’offset à partir de la barre d’outils à l’extrême gauche de masquage automatique sur le côté gauche de la barre d’ancrage.  
  
  
```  
int   m_nAutoHideToolBarMargin;  
```  
  
## <a name="remarks"></a>Notes  
 Le `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` constructeur initialise ce membre à 4 pixels.  
  
## <a name="a-nameafxglobaldatamnautohidetoolbarspacinga-afxglobaldatamnautohidetoolbarspacing"></a><a name="afx_global_data__m_nautohidetoolbarspacing"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
Spécifie l’intervalle entre les barres d’outils de masquage automatique.  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
## <a name="remarks"></a>Notes  
 Le `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` constructeur initialise ce membre à 14 pixels.  
  
## <a name="a-nameafxglobaldatamndragframethicknessdocka-afxglobaldatamndragframethicknessdock"></a><a name="afx_global_data__m_ndragframethicknessdock"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Spécifie l’épaisseur du cadre glisser qui est utilisé pour indiquer l’état d’ancrage.  
  
  
```  
int   m_nDragFrameThicknessDock;  
```  
  
## <a name="remarks"></a>Notes  
 Le `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` constructeur initialise ce membre de 3 pixels.  
  
## <a name="a-nameafxglobaldatamndragframethicknessfloata-afxglobaldatamndragframethicknessfloat"></a><a name="afx_global_data__m_ndragframethicknessfloat"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
Spécifie l’épaisseur du cadre glisser qui est utilisé pour indiquer l’état flottant.  
  
  
```  
int   m_nDragFrameThicknessFloat;  
```  
  
## <a name="remarks"></a>Notes  
 Le `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` constructeur initialise ce membre à 4 pixels.  
  
## <a name="a-nameafxglobaldataonsettingchangea-afxglobaldataonsettingchange"></a><a name="afx_global_data__onsettingchange"></a> AFX_GLOBAL_DATA::OnSettingChange
Détecte l’état actuel des fonctionnalités de masquage automatique de la barre des tâches et de l’animation des menus du Bureau.  
  
  
```  
void OnSettingChange();
```  
  
## <a name="remarks"></a>Notes  
 Cette méthode définit les variables de framework à l’état de certains attributs du bureau de l’utilisateur. Cette méthode détecte l’état actuel de l’animation de menu, atténuation de menu et barre fonctions de masquage automatique des tâches.  
  
## <a name="a-nameafxglobaldataregisterwindowclassa-afxglobaldataregisterwindowclass"></a><a name="afx_global_data__registerwindowclass"></a> AFX_GLOBAL_DATA::RegisterWindowClass
Inscrit la classe de fenêtre MFC spécifiée.  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `lpszClassNamePrefix`  
 Le nom de la classe de fenêtre à inscrire.  
  
## <a name="return-value"></a>Valeur de retour  
 Le nom qualifié de la classe inscrite si cette méthode réussit ; dans le cas contraire, un [exception ressources](../Topic/AfxThrowResourceException.md).  
  
## <a name="remarks"></a>Notes  
 La valeur de retour est une liste délimitée par des deux-points de la `lpszClassNamePrefix` chaîne de paramètre et les représentations sous forme de texte hexadécimal des handles de l’instance actuelle de l’application ; le curseur de l’application, qui est le pointeur dont l’identificateur est IDC_ARROW ; et le pinceau d’arrière-plan. Pour plus d’informations sur l’inscription des classes de fenêtre MFC, consultez [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass).  
  
## <a name="see-also"></a>Voir aussi    
 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="a-nameafxglobaldataresumea-afxglobaldataresume"></a><a name="afx_global_data__resume"></a> AFX_GLOBAL_DATA::Resume
 Réinitialise les pointeurs de fonction interne qui accèdent à des méthodes qui prennent en charge les thèmes Windows et des styles visuels. 
  
  
```  
BOOL Resume();
```  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si cette méthode réussit ; dans le cas contraire, `FALSE`. En mode débogage, cette méthode déclare si cette méthode est infructueuse.  
  
## <a name="remarks"></a>Notes  
 Cette méthode est appelée lorsque l’infrastructure reçoit le [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) message.  
  
## <a name="a-nameafxglobaldatasetlayeredattriba-afxglobaldatasetlayeredattrib"></a><a name="afx_global_data__setlayeredattrib"></a> AFX_GLOBAL_DATA::SetLayeredAttrib
Fournit un moyen simple d’appeler la méthode Windows [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) .  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `hwnd`  
 Handle vers la fenêtre superposée.  
  
 [in] `crKey`  
 Clé de la couleur de transparence qui le [Gestionnaire de fenêtrage](http://msdn.microsoft.com/library/windows/desktop/aa969540) utilise pour composer la fenêtre superposée.  
  
 [in] `bAlpha`  
 La valeur alpha est utilisée pour décrire l’opacité de la fenêtre superposée.  
  
 [in] `dwFlags`  
 Combinaison de bits (OR) d’indicateurs qui spécifient les paramètres de la méthode à utiliser. Spécifiez LWA_COLORKEY pour utiliser le `crKey` paramètre comme la couleur de transparence. LWA_ALPHA permet de spécifier le `bAlpha` paramètre pour déterminer l’opacité de la fenêtre superposée.  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si cette méthode réussit ; dans le cas contraire, `FALSE`.   
 
## <a name="see-also"></a>Voir aussi   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="a-nameafxglobaldatasetmenufonta-afxglobaldatasetmenufont"></a><a name="afx_global_data__setmenufont"></a> AFX_GLOBAL_DATA::SetMenuFont
Crée la police logique spécifiée.  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `lpLogFont`  
 Pointeur vers une structure qui contient les attributs d’une police.  
  
 [in] `bHorz`  
 `TRUE` Pour spécifier que le texte à l’horizontale ; `FALSE` pour spécifier que le texte verticalement.  
  
## <a name="return-value"></a>Valeur de retour  
 `TRUE` Si cette méthode réussit ; dans le cas contraire, `FALSE`. En mode débogage, cette méthode déclare si cette méthode est infructueuse.  
  
## <a name="remarks"></a>Notes  
 Cette méthode crée une police normale horizontale, une police soulignée, et une police en gras est utilisé par défaut des éléments de menu. Cette méthode crée également une police verticale normale. Pour plus d’informations sur les polices logiques, consultez [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#cfont__createfontindirect).  
  
## <a name="a-nameafxglobaldataupdatefontsa-afxglobaldataupdatefonts"></a><a name="afx_global_data__updatefonts"></a> AFX_GLOBAL_DATA::UpdateFonts
Réinitialise les polices logiques qui sont utilisées par l’infrastructure.  
  
  
```  
void UpdateFonts();
```  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations sur les polices logiques, consultez `CFont::CreateFontIndirect`.  
  
## <a name="a-nameafxglobaldataupdatesyscolorsa-afxglobaldataupdatesyscolors"></a><a name="afx_global_data__updatesyscolors"></a> AFX_GLOBAL_DATA::UpdateSysColors
Initialise les couleurs, la profondeur de couleur, les pinceaux, les stylets et les images qui sont utilisés par l’infrastructure.  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="a-nameafxglobaldatabiswindows7a-afxglobaldatabiswindows7"></a><a name="afx_global_data__biswindows7"></a> AFX_GLOBAL_DATA::bIsWindows7
Indique si l’application est en cours d’exécution sous Windows 7 ou version ultérieure.  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="a-nameafxglobaldataclractivecaptiongradienta-afxglobaldataclractivecaptiongradient"></a><a name="afx_global_data__clractivecaptiongradient"></a> AFX_GLOBAL_DATA::clrActiveCaptionGradient
Spécifie la couleur de la légende active. Généralement utilisé pour les volets d’ancrage.  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldataclrinactivecaptiongradienta-afxglobaldataclrinactivecaptiongradient"></a><a name="afx_global_data__clrinactivecaptiongradient"></a> AFX_GLOBAL_DATA::clrInactiveCaptionGradient
Spécifie la couleur de la légende inactive. Généralement utilisé pour les volets d’ancrage.  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldatagetitaskbarlista-afxglobaldatagetitaskbarlist"></a><a name="afx_global_data__getitaskbarlist"></a> AFX_GLOBAL_DATA::GetITaskbarList
Crée et stocke les données globales d’un pointeur vers le `ITaskBarList` interface.  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
## <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `ITaskbarList` Si la création d’une tâche à l’objet de liste de la barre réussit, l’interface `NULL` Si la création échoue ou si le système d’exploitation actuel est inférieur à Windows 7.  
  
## <a name="a-nameafxglobaldatagetitaskbarlist3a-afxglobaldatagetitaskbarlist3"></a><a name="afx_global_data__getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3
Crée et stocke les données globales d’un pointeur vers le `ITaskBarList3` interface.  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
## <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `ITaskbarList3` Si la création d’une tâche à l’objet de liste de la barre réussit, l’interface `NULL` Si la création échoue ou si le système d’exploitation actuel est inférieur à Windows 7.  
  
## <a name="a-nameafxglobaldatagetshellautohidebarsa-afxglobaldatagetshellautohidebars"></a><a name="afx_global_data__getshellautohidebars"></a> AFX_GLOBAL_DATA::GetShellAutohideBars
Détermine les positions des barres de masquage automatique de l’interpréteur de commandes.  
  
  
```  
int GetShellAutohideBars();
```  
  
## <a name="return-value"></a>Valeur de retour  
 Une valeur entière avec encodé indicateurs qui spécifient des positions auto masquer barres. Elle peut combiner les valeurs suivantes : AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.  
  
## <a name="a-nameafxglobaldatareleasetaskbarrefsa-afxglobaldatareleasetaskbarrefs"></a><a name="afx_global_data__releasetaskbarrefs"></a> AFX_GLOBAL_DATA::ReleaseTaskBarRefs
Libère les interfaces obtenues via les `GetITaskbarList` et `GetITaskbarList3` méthodes.  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="a-nameafxglobaldatashellcreateitemfromparsingnamea-afxglobaldatashellcreateitemfromparsingname"></a><a name="afx_global_data__shellcreateitemfromparsingname"></a> AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
Crée et initialise un objet élément d’interpréteur de commandes à partir d’un nom de l’analyse.  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszPath`  
 [in] Pointeur vers un nom d’affichage.  
  
 `pbc`  
 Pointeur vers un contexte de liaison qui contrôle l’opération d’analyse.  
  
 `riid`  
 Une référence à un ID d’interface.  
  
 `ppv`  
 [out] Lorsque cette fonction est retournée, contient le pointeur d’interface demandé dans `riid`. Il s’agit généralement `IShellItem` ou `IShellItem2`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne S_OK si l’opération a réussi ; une valeur d’erreur dans le cas contraire.  

