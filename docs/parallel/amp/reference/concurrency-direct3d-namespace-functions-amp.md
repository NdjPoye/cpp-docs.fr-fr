---
title: "Fonctions d’espace de noms Concurrency::Direct3D (AMP) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 46cafc3c6d6f21eaf147ef0edfeca7f2c81d64e6
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Fonctions d’espace de noms Concurrency::Direct3D (AMP)
||||  
|-|-|-|  
|[ABS (fonction)](#abs)|[Clamp (fonction)](#clamp)|[countbits, fonction](#countbits)|
|[create_accelerator_view, fonction](#create_accelerator_view)|||
|[d3d_access_lock (fonction)](#d3d_access_lock)|[d3d_access_try_lock (fonction)](#d3d_access_try_lock)|[d3d_access_unlock (fonction)](#d3d_access_unlock)|  
|[firstbithigh, fonction](#firstbithigh)|[firstbitlow, fonction](#firstbitlow)|[get_buffer, fonction](#get_buffer)|  
|[Imax, fonction](#imax)|[Imin, fonction](#imin)|[is_timeout_disabled, fonction](#is_timeout_disabled)|  
|[MAD (fonction)](#mad)|[make_array, fonction](#make_array)|[Noise, fonction](#noise)|  
|[radians (fonction)](#radians)|[rcp, fonction](#rcp)|[reversebits, fonction](#reversebits)|  
|[saturate (fonction)](#saturate)|[Sign, fonction](#sign)|[smoothstep, fonction](#smoothstep)|  
|[Step, fonction](#step)|[UMAX, fonction](#umax)|[umin, fonction](#umin)|  
  
##  <a name="a-nameabsa--abs-function"></a><a name="abs"></a>ABS (fonction)  
 Retourne la valeur absolue de l’argument  
  
```  
inline int abs(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur absolue de l’argument.  
  
##  <a name="a-nameclampa--clamp-function"></a><a name="clamp"></a>Clamp (fonction)  
 Calcule la valeur du premier argument spécifié ancrée à une plage définie par les deuxième et le troisième arguments spécifiés.  
  
```  
inline float clamp(
    float _X,  
    float _Min,  
    float _Max) restrict(amp);

 
inline int clamp(
    int _X,  
    int _Min,  
    int _Max) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 La valeur à être ancrée  
  
 `_Min`  
 La limite inférieure de la plage de serrage.  
  
 `_Max`  
 La limite supérieure de la plage de serrage.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur limitée de `_X`.  
  
##  <a name="a-namecountbitsa--countbits-function"></a><a name="countbits"></a>countbits, fonction  
 Compte le nombre de bits de jeu dans _X  
  
```  
inline unsigned int countbits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière non signée  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie le nombre de bits de l’ensemble de _X  

## <a name="a-namecreateacceleratorviewa-createacceleratorview-function"></a><a name="create_accelerator_view"></a>create_accelerator_view, fonction
Crée un [accelerator_view](accelerator-view-class.md) objet à partir d’un pointeur vers une interface de périphérique Direct3D.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
accelerator_view create_accelerator_view(  
    IUnknown * _D3D_device  
    queuing_mode _Qmode = queuing_mode_automatic);  
  
accelerator_view create_accelerator_view(  
    accelerator& _Accelerator,  
    bool _Disable_timeout  
    queuing_mode _Qmode = queuing_mode_automatic);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Accelerator`  
 L’accélérateur sur lequel la nouvelle accelerator_view doit être créé.  
  
 `_D3D_device`  
 Pointeur vers l’interface du périphérique Direct3D.  
  
 `_Disable_timeout`  
 Un paramètre booléen qui spécifie si le délai d’attente doit être désactivée pour l’accelerator_view nouvellement créé. Cela correspond à l’indicateur D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT pour la création du périphérique Direct3D et est utilisée pour indiquer si le système d’exploitation doivent autoriser les charges de travail qui prennent plus de 2 secondes pour s’exécuter sans réinitialiser le périphérique par le mécanisme de récupération et de détection de délai d’attente de Windows. Utilisation de cet indicateur est recommandée si vous avez besoin effectuer des tâches beaucoup de temps sur l’accelerator_view.  
  
 `_Qmode`  
 Le [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) à utiliser pour l’accelerator_view nouvellement créé. Ce paramètre a la valeur par défaut `queuing_mode_automatic`.  
  
## <a name="return-value"></a>Valeur de retour  
 Le `accelerator_view` objet créé à partir de l’interface du périphérique Direct3D passé.  
  
## <a name="remarks"></a>Notes  
 Cette fonction crée un nouveau `accelerator_view` objet d’un pointeur existant à une interface de périphérique Direct3D. Si l’appel de fonction aboutit, le décompte de références du paramètre est incrémenté d’un `AddRef` appel à l’interface. Vous pouvez libérer en toute sécurité de l’objet lorsqu’il n’est plus nécessaire dans votre code de DirectX. Si l’appel de méthode échoue, un [runtime_exception](runtime-exception-class.md) est levée.  
  
 Le `accelerator_view` objet que vous créez à l’aide de cette fonction est thread-safe. Vous devez synchroniser l’utilisation simultanée de la `accelerator_view` objet. Non synchronisé utilisation simultanée de la `accelerator_view` objet et l’interface ID3D11Device brute provoque un comportement non défini.  
  
 Le runtime C++ AMP fournit des informations détaillées en mode débogage à l’aide de la couche de débogage D3D si vous utilisez la `D3D11_CREATE_DEVICE_DEBUG` indicateur.  
  
  
##  <a name="a-named3daccesslocka--d3daccesslock-function"></a><a name="d3d_access_lock"></a>d3d_access_lock (fonction)  
 Acquérir un verrou sur une accelerator_view afin d’exécuter des opérations D3D sur des ressources partagées entre les accelerator_view en toute sécurité. L’accelerator_view et toutes les ressources de C++ AMP en interne associés à cette accelerator_view prennent ce verrou lors de l’exécution des opérations et se bloque pendant qu’un autre thread détient le verrou d’accès D3D. Ce verrou est non récursive : elle est un comportement non défini pour appeler cette fonction à partir d’un thread qui détient déjà le verrou. Il est un comportement non défini pour effectuer des opérations sur les accelerator_view ou n’importe quel conteneur de données associé à l’accelerator_view à partir du thread qui détient le verrou d’accès D3D. Voir aussi scoped_d3d_access_lock, une classe de type RAII pour un verrou d’accès D3D étendue.  
  
```  
void __cdecl d3d_access_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Av`  
 Accelerator_view à verrouiller.  
  
##  <a name="a-named3daccesstrylocka--d3daccesstrylock-function"></a><a name="d3d_access_try_lock"></a>d3d_access_try_lock (fonction)  
 Tenter d’acquérir le verrou d’accès D3D sur une accelerator_view sans se bloquer.  
  
```  
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Av`  
 Accelerator_view à verrouiller.  
  
### <a name="return-value"></a>Valeur de retour  
 la valeur True si le verrou a été acquis, ou false si elle est actuellement détenu par un autre thread.  
  
##  <a name="a-named3daccessunlocka--d3daccessunlock-function"></a><a name="d3d_access_unlock"></a>d3d_access_unlock (fonction)  
 Déverrouiller l’accès D3D l’accelerator_view donné. Si le thread appelant ne contient pas le verrou sur l’accelerator_view les résultats sont indéfinis.  
  
```  
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Av`  
 L’accelerator_view pour laquelle le verrou peut être libéré.  
  
##  <a name="a-namefirstbithigha--firstbithigh-function"></a><a name="firstbithigh"></a>firstbithigh, fonction  
 Obtient l’emplacement du premier bit ensemble dans _X, commençant par le bit d’ordre le plus élevé et le déplacement vers le bit d’ordre le plus bas.  
  
```  
inline int firstbithigh(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 L’emplacement du premier bit d’ensemble  
  
##  <a name="a-namefirstbitlowa--firstbitlow-function"></a><a name="firstbitlow"></a>firstbitlow, fonction  
 Obtient l’emplacement du premier bit ensemble dans _X, en commençant avec le bit d’ordre le plus bas et vers le bit d’ordre le plus élevé.  
  
```  
inline int firstbitlow(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’emplacement du premier bit défini  
  
##  <a name="a-namegetbuffera--getbuffer-function"></a><a name="get_buffer"></a>get_buffer, fonction  
 Obtenir l’interface de mémoire tampon Direct3D sous-jacent du tableau spécifié.  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;  
```  
  
### <a name="parameters"></a>Paramètres  
 `value_type`  
 Type des éléments dans le tableau.  
  
 `_Rank`  
 Le rang du tableau.  
  
 `_Array`  
 Un tableau sur une accelerator_view Direct3D pour lequel l’interface de mémoire tampon Direct3D sous-jacent est retourné.  
  
### <a name="return-value"></a>Valeur de retour  
 Le pointeur d’interface IUnknown correspondant à la mémoire tampon de Direct3D sous-jacent du tableau.  
  
##  <a name="a-nameimaxa--imax-function"></a><a name="imax"></a>Imax, fonction  
 Déterminer la valeur numérique maximale des arguments  
  
```  
inline int imax(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
 `_Y`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourner la valeur numérique maximale des arguments  
  
##  <a name="a-nameimina--imin-function"></a><a name="imin"></a>Imin, fonction  
 Déterminer la valeur numérique minimale des arguments  
  
```  
inline int imin(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
 `_Y`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourner la valeur numérique minimale des arguments  
  
##  <a name="a-nameistimeoutdisableda--istimeoutdisabled-function"></a><a name="is_timeout_disabled"></a>is_timeout_disabled, fonction  
 Retourne un indicateur booléen indiquant si le délai d’attente est désactivée pour l’accelerator_view spécifié. Cela correspond à l’indicateur D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT pour la création du périphérique Direct3D.  
  
```  
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Accelerator_view`  
 L’accelerator_view pour lequel le paramètre de délai désactivé doit être interrogé.  
  
### <a name="return-value"></a>Valeur de retour  
 Un indicateur booléen indiquant si le délai d’attente est désactivée pour l’accelerator_view spécifié.  
  
##  <a name="a-namemada--mad-function"></a><a name="mad"></a>MAD (fonction)  
 Calcule le produit de la première et deuxième argument spécifié, puis ajoute le troisième argument spécifié.  
  
```  
inline float mad(
    float _X,  
    float _Y,  
    float _Z) restrict(amp);

 
inline double mad(
    double _X,  
    double _Y,  
    double _Z) restrict(amp);

 
inline int mad(
    int _X,  
    int _Y,  
    int _Z) restrict(amp);

 
inline unsigned int mad(
    unsigned int _X,  
    unsigned int _Y,  
    unsigned int _Z) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Le premier argument spécifié.  
  
 `_Y`  
 Le deuxième argument spécifié.  
  
 `_Z`  
 Le troisième argument spécifié.  
  
### <a name="return-value"></a>Valeur de retour  
 The result of `_X` * `_Y` + `_Z`.  
  
##  <a name="a-namemakearraya--makearray-function"></a><a name="make_array"></a>make_array, fonction  
 Créer un tableau à partir d’un pointeur d’interface de mémoire tampon Direct3D.  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
array<value_type, _Rank> make_array(
    const extent<_Rank>& _Extent,  
    const Concurrency::accelerator_view& _Rv,  
    IUnknown* _D3D_buffer)  ;  
```  
  
### <a name="parameters"></a>Paramètres  
 `value_type`  
 Le type d’élément du tableau doit être créé.  
  
 `_Rank`  
 Le rang du tableau doit être créé.  
  
 `_Extent`  
 Une étendue qui décrit la forme de l’agrégat du tableau.  
  
 `_Rv`  
 Vue d’accélérateur D3D sur laquelle le tableau doit être créé.  
  
 `_D3D_buffer`  
 Pointeur d’interface IUnknown de la mémoire tampon D3D pour créer le tableau à partir de.  
  
### <a name="return-value"></a>Valeur de retour  
 Un tableau est créé à l’aide de la mémoire tampon Direct3D fournie.  
  
##  <a name="a-namenoisea--noise-function"></a><a name="noise"></a>Noise, fonction  
 Génère une valeur aléatoire à l’aide de l’algorithme de bruit Perlin  
  
```  
inline float noise(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante à partir de laquelle le bruit Perlin  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de bruit Perlin le dans une plage comprise entre -1 et 1  
  
##  <a name="a-nameradiansa--radians-function"></a><a name="radians"></a>radians (fonction)  
 Convertit _X de degrés en radians  
  
```  
inline float radians(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X convertie à partir de degrés en radians  
  
##  <a name="a-namercpa--rcp-function"></a><a name="rcp"></a>rcp, fonction  
 Calcule l’inverse de l’argument spécifié à l’aide d’une approximation rapide.  
  
```  
inline float rcp(float _X) restrict(amp);

 
inline double rcp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 La valeur pour laquelle calculer la réciproque.  
  
### <a name="return-value"></a>Valeur de retour  
 L’inverse de l’argument spécifié.  
  
##  <a name="a-namereversebitsa--reversebits-function"></a><a name="reversebits"></a>reversebits, fonction  
 Inverse l’ordre des octets dans _X  
  
```  
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière non signée  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur avec l’ordre de bit inversée dans _X  
  
##  <a name="a-namesaturatea--saturate-function"></a><a name="saturate"></a>saturate (fonction)  
 Crochets _X dans la plage de 0 à 1.  
  
```  
inline float saturate(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X ancrée dans la plage de 0 à 1.  
  
##  <a name="a-namesigna--sign-function"></a><a name="sign"></a>Sign, fonction  
 Détermine le signe de l’argument spécifié.  
  
```  
inline int sign(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Le signe de l’argument.  
  
##  <a name="a-namesmoothstepa--smoothstep-function"></a><a name="smoothstep"></a>smoothstep, fonction  
 Renvoie une interpolation d’Hermite lisse entre 0 et 1, si _X se trouve dans la plage [_Min, _Max].  
  
```  
inline float smoothstep(
    float _Min,  
    float _Max,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Min`  
 Valeur à virgule flottante  
  
 `_Max`  
 Valeur à virgule flottante  
  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne 0 si _X est inférieure à _Min ; 1 si _X est supérieure à _Max ; Sinon, une valeur comprise entre 0 et 1 si _X se trouve dans la plage [_Min, _Max]  
  
##  <a name="a-namestepa--step-function"></a><a name="step"></a>Step, fonction  
 Compare deux valeurs de retour de 0 ou 1 selon que la valeur est supérieure  
  
```  
inline float step(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Y`  
 Valeur à virgule flottante  
  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne 1 si le _X est supérieur ou égal à _Y ; Sinon, 0  
  
##  <a name="a-nameumaxa--umax-function"></a><a name="umax"></a>UMAX, fonction  
 Déterminer la valeur numérique maximale des arguments  
  
```  
inline unsigned int umax(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
 `_Y`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourner la valeur numérique maximale des arguments  
  
##  <a name="a-nameumina--umin-function"></a><a name="umin"></a>umin, fonction  
 Déterminer la valeur numérique minimale des arguments  
  
```  
inline unsigned int umin(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
 `_Y`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourner la valeur numérique minimale des arguments  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Direct3D Namespace](concurrency-direct3d-namespace.md)

