<!-- README.md is generated from README.Rmd. Please edit that file -->

# hexSticker: create hexagon sticker in R

[![CRAN_Status_Badge](http://www.r-pkg.org/badges/version/hexSticker?color=green)](https://cran.r-project.org/package=hexSticker)
[![](http://cranlogs.r-pkg.org/badges/grand-total/hexSticker?color=green)](https://cran.r-project.org/package=hexSticker)
[![](http://cranlogs.r-pkg.org/badges/hexSticker?color=green)](https://cran.r-project.org/package=hexSticker)
[![](http://cranlogs.r-pkg.org/badges/last-week/hexSticker?color=green)](https://cran.r-project.org/package=hexSticker)

## :writing_hand: Author

Guangchuang YU <https://yulab-smu.top>

School of Basic Medical Sciences, Southern Medical University

[![saythanks](https://img.shields.io/badge/say-thanks-ff69b4.svg)](https://saythanks.io/to/GuangchuangYu)
[![](https://img.shields.io/badge/follow%20me%20on-WeChat-green.svg)](https://guangchuangyu.github.io/blog_images/biobabble.jpg)

------------------------------------------------------------------------

## :arrow_double_down: Installation

Install the hexSticker package via CRAN:

``` r
install.packages("hexSticker")
```

You can also install the package via the Github repository.

``` r
# install.package("remotes")   #In case you have not installed it.
remotes::install_github("GuangchuangYu/hexSticker")
```

## Fail to install

### imageMagick

`imageMagick` is required for installing `hexSticker`. If you have not
installed it, please try the following
[approaches](https://www.imagemagick.org/script/download.php).

### Fail to load ‘sysfonts’

In Mac OS, you may need to re-install `sysfont` to properly load it.

Be sure to install `xquartz` first.

``` r
brew update && brew install homebrew/cask/xquartz
```

------------------------------------------------------------------------

## Examples

> `sticker` function will produce a file with dimension exactly for
> printing according to <http://hexb.in/sticker.html>

### base plot

``` r
library(hexSticker)
s <- sticker(~plot(cars, cex=.5, cex.axis=.5, mgp=c(0,.3,0), xlab="", ylab=""),
          package="hexSticker", p_size=20, s_x=.8, s_y=.6, s_width=1.4, s_height=1.2,
          filename="inst/figures/baseplot.png")
```

The `sticker()` will generate a figure specified by the `filename`
parameter. The output of the `sticker()` function is a `ggplot` object,
e.g. the `s` variable in the above example. Print the object,
`print(s)`, will display the image. However, the image may slightly
different from the created image file since the graphic device size are
different. To solve this issue, `hexSticker` package provides `plot`
function to preview sticker. Try `plot(s)` :).

<img src="inst/figures/baseplot.png" height="300"/>

### lattice

``` r
library(lattice)

counts <- c(18,17,15,20,10,20,25,13,12)
outcome <- gl(3,1,9)
treatment <- gl(3,3)
bwplot <- bwplot(counts ~ outcome | treatment, xlab=NULL, ylab=NULL, cex=.5,
                 scales=list(cex=.5), par.strip.text=list(cex=.5))
sticker(bwplot, package="hexSticker", p_size=20, s_x=1.05, s_y=.8, s_width=2, s_height=1.5,
        h_fill="#f9690e", h_color="#f39c12", filename="inst/figures/lattice.png")
```

<img src="inst/figures/lattice.png" height="300"/>

### ggplot2

``` r
library(ggplot2)

p <- ggplot(aes(x = mpg, y = wt), data = mtcars) + geom_point()
p <- p + theme_void() + theme_transparent()

sticker(p, package="hexSticker", p_size=20, s_x=1, s_y=.75, s_width=1.3, s_height=1,
        filename="inst/figures/ggplot2.png")
```

<img src="inst/figures/ggplot2.png" height="300"/>

### image file

``` r
imgurl <- system.file("figures/cat.png", package="hexSticker")
sticker(imgurl, package="hexSticker", p_size=20, s_x=1, s_y=.75, s_width=.6,
        filename="inst/figures/imgfile.png")
```

<img src="inst/figures/imgfile.png" height="300"/>

### Google fonts

``` r
library(showtext)
## Loading Google fonts (http://www.google.com/fonts)
font_add_google("Gochi Hand", "gochi")
## Automatically use showtext to render text for future devices
showtext_auto()

## use the ggplot2 example
sticker(p, package="hexSticker", p_size=22, s_x=1, s_y=.75, s_width=1.3, s_height=1,
        p_family = "gochi", filename="inst/figures/ggplot2-google-font.png")
```

<img src="inst/figures/ggplot2-google-font.png" height="300"/>

------------------------------------------------------------------------

## :sparkling_heart: Stickers produced by `hexSticker`

> If you use `hexSticker` and want your sticker to be listed here,
> please feel free to edit
> [README.Rmd](https://github.com/GuangchuangYu/hexSticker/edit/master/README.Rmd),
> and run
> `rmarkdown::render("README.Rmd", rmarkdown::md_document(variant = "gfm"))`
> in `R` to generate `README.md`.

**Please put stickers in alphabet order.**

### Stickers for software packages

<!--
[<img src="" height="120"/>]()
-->

[<img src="https://raw.githubusercontent.com/furrer-lab/abn/refs/heads/main/inst/figures/logo.png" height="120"/>](https://github.com/furrer-lab/abn)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/AnnotationFilter/AnnotationFilter_hl.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/AnnotationFilter)
[<img src="https://github.com/lpantano/bcbioSmallRna/raw/master/inst/sticker/bcbioSmallRna.png" height="120"/>](https://github.com/lpantano/bcbioSmallRna)
[<img src="https://raw.githubusercontent.com/bcgov/bcmaps/master/inst/sticker/bcmaps.png" height="120"/>](https://github.com/bcgov/bcmaps)
[<img src="https://raw.githubusercontent.com/danielmarcelino/CamaraBR/master/inst/figures/CamaraBR-logo.png" height="120"/>](https://github.com/danielmarcelino/CamaraBR)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/ChIPseeker/ChIPseeker.png" height="120"/>](https://github.com/GuangchuangYu/ChIPseeker)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/cleaver/cleaver.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/cleaver)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/clusterProfiler/clusterProfiler.png" height="120"/>](https://github.com/GuangchuangYu/clusterProfiler)
[<img src="https://raw.githubusercontent.com/SGS2000/ClustMC/master/man/figures/logo.png" height="120"/>](https://github.com/SGS2000/ClustMC)
[<img src="https://raw.githubusercontent.com/stevecondylios/collidr/master/man/figures/collidr.png" height="120"/>](https://github.com/stevecondylios/collidr)
[<img src="https://github.com/RhoInc/CRANsearcher/raw/master/inst/image/hex/CRANsearcher_hexSticker.png" height="120"/>](https://github.com/RhoInc/CRANsearcher)
[<img src="https://github.com/sstoeckl/crypto2/raw/master/man/figures/crypto2_hex.png" height="120"/>](https://github.com/sstoeckl/crypto2)
[<img src="https://raw.githubusercontent.com/nathansam/datefixR/main/man/figures/sticker.png " height="120"/>](https://github.com/nathansam/DatefixR)
[<img src="https://raw.githubusercontent.com/eikeluedeling/decisionSupport/master/vignettes/decisionSupport.png" height="120"/>](https://cran.r-project.org/web/packages/decisionSupport/index.html)
[<img src="https://raw.githubusercontent.com/lpantano/DEGreport/main/inst/sticker/degreport.png" height="120"/>](https://github.com/lpantano/DEGreport)
[<img src="https://raw.githubusercontent.com/villegar/dive/master/inst/images/logo.png" height="120"/>](https://github.com/villegar/dive)
[<img src="https://github.com/tbradley1013/dragondown/raw/master/man/figures/dragondown.png" height="120"/>](https://github.com/tbradley1013/dragondown)
[<img src="https://github.com/calcita/ech/blob/master/man/figures/ech_logo.png" height="120"/>](https://github.com/calcita/ech)
[<img src="https://github.com/mrchypark/elbird/raw/main/man/figures/logo.png" height="120"/>](https://github.com/mrchypark/elbird)
[<img src="https://raw.githubusercontent.com/lance-waller-lab/envi/main/man/figures/envi.png" height="120"/>](https://github.com/Waller-SUSAN/envi)
[<img src="https://raw.githubusercontent.com/asilatakarandikar/eparlibscrapR/main/man/figures/logo.png" height="120"/>](https://github.com/asilatakarandikar/eparlibscrapR/)
[<img src="https://raw.githubusercontent.com/CWWhitney/ethnobotanyR/master/vignettes/ethnobotanyR.png" height="120"/>](https://github.com/CWWhitney/ethnobotanyR)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/FamAgg/FamAgg_hl.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/FamAgg)
[<img src="https://github.com/lschneiderbauer/fCWTr/raw/master/man/figures/logo.svg" height="120"/>](https://lschneiderbauer.github.io/fCWTr/)
[<img src="https://github.com/sstoeckl/ffdownload/raw/master/man/figures/logo.png" height="120"/>](https://github.com/sstoeckl/ffdownload)
[<img src="https://github.com/wangjiaxuan666/fixbatch/blob/main/man/figures/fixbatch_hexSticker.png" height="120"/>](https://github.com/wangjiaxuan666/fixbatch)
[<img src="https://raw.githubusercontent.com/JeffreyRStevens/flashr/main/man/figures/logo.png" height="120"/>](https://github.com/JeffreyRStevens/flashr)
[<img src="https://raw.githubusercontent.com/lance-waller-lab/gateR/main/man/figures/gateR.png" height="120"/>](https://github.com/Waller-SUSAN/gateR)
[<img src="https://raw.githubusercontent.com/Matheusbp/GemirTools/master/man/figures/logo.png" height="120"/>](https://github.com/Matheusbp/GemirTools)
[<img src="https://github.com/ipeaGIT/geobr/raw/master/r-package/man/figures/geobr_logo_b.png" height="120"/>](https://github.com/ipeaGIT/geobr)
[<img src="https://github.com/RichDeto/geouy/blob/master/man/figures/geouy_logo_b.png" height="120"/>](https://github.com/RichDeto/geouy)
[<img src="https://www.samabbott.co.uk/getTBinR/reference/figures/logo.png" height="120"/>](https://www.samabbott.co.uk/getTBinR/)
[<img src="https://raw.githubusercontent.com/strengejacke/ggeffects/master/man/figures/logo.png" height="120"/>](https://github.com/strengejacke/ggeffects)
[<img src="https://raw.githubusercontent.com/rivasiker/ggHoriPlot/master/man/images/sticker_ggHoriPlot.png" height="120"/>](https://rivasiker.github.io/ggHoriPlot/)
[<img src="https://raw.githubusercontent.com/mikmart/ggragged/main/man/figures/logo.png" height="120"/>](https://github.com/mikmart/ggragged)
[<img src="https://raw.githubusercontent.com/botan/ggrounded/main/man/figures/logo.png" height="120"/>](https://github.com/botan/ggrounded)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/ggtree/ggtree.png" height="120"/>](https://github.com/GuangchuangYu/ggtree)
[<img src="https://raw.githubusercontent.com/MEDSL/resources/master/images/ggmedsl.png" height="120"/>](https://github.com/MEDSL/ggmedsl)
[<img src="https://raw.githubusercontent.com/dieghernan/giscoR/master/man/figures/logo.png" height="120"/>](https://github.com/dieghernan/giscoR)
[<img src="https://github.com/muschellij2/glassdoor/raw/master/sticker.png" height="120"/>](https://github.com/muschellij2/glassdoor)
[<img src="https://github.com/montesmariana/glossr/raw/main/man/figures/logo.png" height="120"/>](https://github.com/montesmariana/glossr)
[<img src="https://github.com/greta-dev/greta/raw/master/logos/greta_hex.png" height="120"/>](https://github.com/greta-dev/greta/tree/master/logos)
[<img src="https://raw.githubusercontent.com/calvinmfloyd/grobblR/master/man/figures/logo.png" height="120"/>](https://github.com/calvinmfloyd/grobblR)
[<img src="https://raw.githubusercontent.com/mikemahoney218/heddlr/master/man/figures/heddlr-badge.png" height="120"/>](https://github.com/mikemahoney218/heddlr)
[<img src="https://raw.githubusercontent.com/dieghernan/igoR/master/man/figures/logo.png" height="120"/>](https://github.com/dieghernan/igoR)
[<img src="https://raw.githubusercontent.com/SteffenMoritz/imputeR/master/man/figures/imputeR-logo.png" height="120"/>](https://github.com/SteffenMoritz/imputeR)
[<img src="https://raw.githubusercontent.com/lpantano/isomiRs/178974f22801ffcb68393971e4d072d367938f05/inst/stickers/isomirs.png" height="120"/>](https://github.com/lpantano/isomiRs)
[<img src="https://github.com/igorlaltuf/ispdata/blob/main/man/figures/logo.png" height="120"/>](https://github.com/igorlaltuf/ispdata)
[<img src="https://raw.githubusercontent.com/wjakethompson/jayhawkdown/master/man/figures/jayhawkdown.png" height="120"/>](https://github.com/wjakethompson/jayhawkdown)
[<img src="https://github.com/graemeleehickey/joineR/raw/master/man/figures/hex.png" height="120"/>](https://github.com/graemeleehickey/joineR)
[<img src="https://github.com/graemeleehickey/joineRML/raw/master/man/figures/hex.png" height="120"/>](https://github.com/graemeleehickey/joineRML)
[<img src="https://raw.githubusercontent.com/juliasilge/janeaustenr/master/tools/janeaustenr.png" height="120"/>](https://github.com/juliasilge/janeaustenr/tree/master/tools)
[<img src="https://github.com/cjclarke98/JSUparameters/blob/main/JSUparameters_hex.png" height="120"/>](https://cran.r-project.org/package=JSUparameters)
[<img src="https://github.com/le-huynh/lehuynh/blob/master/man/figures/logo.png?raw=true" height="120"/>](https://le-huynh.github.io/lehuynh/)
[<img src="https://raw.githubusercontent.com/nelson-n/lmForc/main/vignettes/logo/lmForc_hexSticker.png" height="120"/>](https://github.com/nelson-n/lmForc)
[<img src="https://github.com/ryansar/lungct/raw/master/inst/extdata/logo.png" height="120"/>](https://github.com/ryansar/lungct)
[<img src="https://github.com/nlmixrdevelopment/lotri/raw/master/man/figures/logo.png" height="120"/>](https://github.com/nlmixrdevelopment/lotri)
[<img src="https://raw.githubusercontent.com/paezha/macdown/master/man/figures/macdown.png" height="120"/>](https://github.com/paezha/macdown)
[<img src="https://raw.githubusercontent.com/rOpenSpain/mapSpain/master/man/figures/logo.png" height="120"/>](https://github.com/rOpenSpain/mapSpain)
[<img src="https://raw.githubusercontent.com/gpaux/Mediana/master/inst/figures/hexMediana.png" height="120"/>](https://github.com/gpaux/Mediana)
[<img src="https://raw.githubusercontent.com/nrennie/messy/main/man/figures/logo.png" height="120"/>](https://github.com/nrennie/messy)
[<img src="https://github.com/nvietto/movienight/blob/master/man/figures/movienight.png" height="120"/>](https://github.com/nvietto/movienight)
[<img src="https://github.com/keblu/MSGARCH/raw/master/hexmsgarch_small.png" height="120"/>](https://github.com/keblu/MSGARCH)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/MSnbase/MSnbase.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/MSnbase)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/mzR/mzR_hl.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/mzR)
[<img src="https://raw.githubusercontent.com/lbenz730/ncaahoopR/master/figures/logo.png" height="120"/>](https://github.com/lbenz730/ncaahoopR)
[<img src="https://shanmdphd.github.io/hex/ncarbe.png" height="120"/>](https://github.com/asancpt/ncarbe)
[<img src="https://user-images.githubusercontent.com/20061736/81393545-d662c680-9120-11ea-9963-a737f963bd8d.png" height="120"/>](https://mirkosignorelli.github.io/r.html)
[<img src="https://raw.githubusercontent.com/stevecondylios/netstat/master/man/figures/netstat.png" height="120"/>](https://github.com/stevecondylios/netstat)
[<img src="https://raw.githubusercontent.com/nhs-r-community/NHSRdatasets/main/inst/images/nhsrdatasetslogo.png" height="120"/>](https://github.com/nhs-r-community/NHSRdatasets)
[<img src="https://raw.githubusercontent.com/nhs-r-community/NHSRepisodes/main/inst/images/nhsrepisodeslogo.png" height="120"/>](https://github.com/nhs-r-community/NHSRepisodes)
[<img src="https://raw.githubusercontent.com/nhs-r-community/NHSRplotthedots/main/inst/images/logo.png" height="120"/>](https://github.com/nhs-r-community/NHSRplotthedots)
[<img src="https://raw.githubusercontent.com/nhs-r-community/NHSRtheme/main/inst/images/nhsrthemelogo.png" height="120"/>](https://github.com/nhs-r-community/NHSRtheme)
[<img src="https://shanmdphd.github.io/hex/NonCompart.png" height="120"/>](https://github.com/asancpt/NonCompart)
[<img src="https://github.com/nvietto/nopunintended/blob/master/man/logo.png" height="120"/>](https://github.com/nvietto/nopunintended)
[<img src="https://raw.githubusercontent.com/covid19br/nowcaster/main/man/figures/nowcaster_rev.png" height="120"/>](https://github.com/covid19br/nowcaster)
[<img src="https://github.com/emsweene/oasis/raw/master/sticker.png" height="120"/>](https://github.com/emsweene/oasis)
[<img src="https://github.com/StatsGary/OddsPlotty/blob/master/man/figures/OddsPlotty.png" height="120"/>](https://github.com/StatsGary/OddsPlotty)
[<img src="https://raw.githubusercontent.com/EnriquePH/OEIS.R/master/sticker/OEIS.R-sticker.png" height="120"/>](https://github.com/EnriquePH/OEIS.R)
[<img src="https://raw.githubusercontent.com/ox-it/oidnChaRts/master/data-raw/oidnChaRt-sticker.png" height="120"/>](https://github.com/ox-it/oidnChaRts/tree/master/data-raw)
[<img src="https://raw.githubusercontent.com/RGLab/openCyto/master/logo_mid.png" height="120"/>](http://github.com/RGLab/openCyto)
[<img src="https://github.com/DARTH-git/OpenTree/blob/main/openLogo.png" height="120"/>](https://github.com/DARTH-git/OpenTree)
[<img src="https://github.com/cosimameyer/overviewR/blob/master/man/figures/logo.png" height="120"/>](https://github.com/cosimameyer/overviewR)
[<img src="https://user-images.githubusercontent.com/20061736/162180793-072613f0-a93e-4ef6-b0c4-b8d8a45d770a.png" height="120"/>](https://mirkosignorelli.github.io/r.html)
[<img src="https://raw.githubusercontent.com/cbg-ethz/perturbatr/122cdd1516aa13d967677050dbf4fe08cfe66c7c/inst/figure/sticker.png" height="120"/>](https://github.com/cbg-ethz/perturbatr)
[<img src="https://raw.githubusercontent.com/uptake/pkgnet/master/man/figures/logo.png" height="120"/>](https://uptake.github.io/pkgnet/)
[<img src="https://raw.githubusercontent.com/Fifis/pnd/master/inst/figures/pnd-logo.png" height="120"/>](https://github.com/Fifis/pnd)
[<img src="https://raw.githubusercontent.com/dmi3kno/polite/master/data-raw/sticker.png" height="120"/>](https://github.com/dmi3kno/polite)
[<img src="https://raw.githubusercontent.com/nrennie/PrettyCols/main/man/figures/logo.png" height="120"/>](https://github.com/nrennie/PrettCyCols)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/pRoloc/pRoloc.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/pRoloc)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/pRoloc/pRolocdata.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/pRoloc)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/pRoloc/pRolocGUI.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/pRoloc)
[<img src="https://user-images.githubusercontent.com/20061736/84284787-f3821f00-ab3c-11ea-85a7-220982ce518c.png" height="120"/>](https://mirkosignorelli.github.io/r.html)
[<img src="https://github.com/Yue-Jiang/pzfx/raw/master/man/figures/logo.png" height="120"/>](https://github.com/Yue-Jiang/pzfx)
[<img src="https://raw.githubusercontent.com/justinmillar/r-gators-hex/master/r-gators.png" height="120"/>](https://github.com/justinmillar/r-gators-hex)
[<img src="https://raw.githubusercontent.com/jorvlan/open-visualizations/master/R/package_figures/rainclouds_highres.png" height="120"/>](https://github.com/jorvlan/raincloudplots)
[<img src="https://raw.githubusercontent.com/stevecondylios/rawr/master/man/figures/rawr.png" height="120"/>](https://github.com/stevecondylios/rawr)
[<img src="https://raw.githubusercontent.com/jwood000/RcppAlgos/main/man/figures/RcppAlgos-logo.png" height="120"/>](https://github.com/jwood000/RcppAlgos)
[<img src="https://github.com/nvietto/Rdune/blob/main/man/figures/logo.jpg" height="120"/>](https://github.com/nvietto/Rdune)
[<img src="https://github.com/potterzot/rnassqs/raw/master/inst/figures/rnassqs.png" height="120"/>](https://github.com/potterzot/rnassqs)
[<img src="https://raw.githubusercontent.com/prdm0/ropenblas/master/logo.png" height="120"/>](https://github.com/prdm0/ropenblas)
[<img src="https://raw.githubusercontent.com/ellessenne/rsimsum/master/man/figures/hex.png" height="120"/>](https://github.com/ellessenne/rsimsum)
[<img src="https://raw.githubusercontent.com/nrennie/RSSthemes/main/man/figures/logo.png" height="120"/>](https://github.com/nrennie/RSSthemes)
[<img src="https://raw.githubusercontent.com/QiHongchao/SampleSize4ClinicalTrials/master/man/logo/logo.png" height="120"/>](https://github.com/QiHongchao/SampleSize4ClinicalTrials)
[<img src="https://github.com/nvietto/samplezoo/blob/main/man/figures/logo.png" height="120"/>](https://github.com/nvietto/samplezoo)
[<img src="https://github.com/SchlossLab/schtools/raw/main/man/figures/logo.png" height="120"/>](https://github.com/SchlossLab/schtools)
[<img src="https://github.com/thiyangt/seer/raw/master/logo/seer.png" height="120"/>](https://github.com/thiyangt/seer/raw/master/logo/seer.png)
[<img src="https://github.com/sborms/sentometrics/raw/master/man/figures/logo.png" height="120"/>](https://github.com/sborms/sentometrics)
[<img src="https://raw.githubusercontent.com/IyarLin/simMixedDAG/master/inst/simMixedDAGhex.png" height="120"/>](https://github.com/IyarLin/simMixedDAG)
[<img src="https://user-images.githubusercontent.com/9893806/34084712-02f8698a-e33a-11e7-86e7-ce60bf51fe86.png" height="120"/>](https://github.com/Bohdan-Khomtchouk/shinyheatmap)
[<img src="https://raw.githubusercontent.com/cwthom/shinyhelper/master/data-raw/shinyhelper.png" height="120"/>](https://github.com/cwthom/shinyhelper)
[<img src="https://github.com/ShixiangWang/sigminer/raw/master/inst/figures/sigminer.png" height="120"/>](https://github.com/ShixiangWang/sigminer)
[<img src="https://raw.githubusercontent.com/strengejacke/sjmisc/master/man/figures/logo.png" height="120"/>](https://github.com/strengejacke/sjmisc)
[<img src="https://raw.githubusercontent.com/strengejacke/sjPlot/master/man/figures/logo.png" height="120"/>](https://github.com/strengejacke/sjPlot)
[<img src="https://raw.githubusercontent.com/strengejacke/sjstats/master/man/figures/logo.png" height="120"/>](https://github.com/strengejacke/sjstats)
[<img src="https://github.com/Tazinho/snakecase/raw/master/man/figures/snakecase05.png" height="120" />](https://github.com/Tazinho/snakecase)
[<img src="https://raw.githubusercontent.com/danielmarcelino/SoundexBR/master/inst/figures/SoundexBR-logo.png" height="120"/>](https://github.com/danielmarcelino/SoundexBR)
[<img src="https://raw.githubusercontent.com/pdrhlik/southparkr/master/sticker/southparkr-sticker.png" height="120" />](https://github.com/pdrhlik/southparkr)
[<img src="https://raw.githubusercontent.com/rOpenSpain/spanish/master/man/figures/logo.png" height="120"/>](https://github.com/rOpenSpain/spanish)
[<img src="https://github.com/machiela-lab/sparrpowR/blob/master/man/figures/sparrpowR.png" height="120" />](https://github.com/machiela-lab/sparrpowR)
[<img src="https://raw.githubusercontent.com/HaydenMacDonald/squashinformr/master/man/figures/logo.png" height="120" />](https://github.com/HaydenMacDonald/squashinformr)
[<img src="https://github.com/rrrlw/TDAstats/raw/master/man/figures/HexTDA.png" height="120" />](https://github.com/rrrlw/TDAstats)
[<img src="https://raw.githubusercontent.com/rOpenSpain/tidyBdE/master/man/figures/logo.png" height="120"/>](https://github.com/rOpenSpain/mapSpain)
[<img src="https://github.com/taxonomicallyinformedannotation/tima-r/blob/main/man/figures/logo.svg" height="120"/>](https://github.com/taxonomicallyinformedannotation/tima-r)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/treeio/treeio.png" height="120"/>](https://www.bioconductor.org/packages/treeio)
[<img src="https://raw.githubusercontent.com/wenlong-liu/usfertilizer_sticker/master/usfertilizer.png" height="120"/>](https://github.com/wenlong-liu/usfertilizer)
[<img src="https://raw.githubusercontent.com/sjmgarnier/viridis/master/hex_logo/viridis.png" height="120"/>](https://github.com/sjmgarnier/viridis)
[<img src="https://github.com/neuroconductor/WhiteStripe/raw/master/sticker.png" height="120"/>](https://github.com/neuroconductor/WhiteStripe)
[<img src="https://github.com/JaseZiv/worldfootballR/blob/main/man/figures/logo.png" height="120"/>](https://github.com/JaseZiv/worldfootballR)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/xcms/xcms_hl.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/xcms)
[<img src="https://raw.githubusercontent.com/drisso/zinb_analysis/master/sticker/zinbwave.png" height="120"/>](https://github.com/drisso/zinb_analysis/tree/master/sticker)

### Stickers for events/workshops

[<img src="https://github.com/MonkmanMH/UVic_BIDA302/blob/main/hex_sticker/BIDA302_hex.png" height="120"/>](https://github.com/MonkmanMH/UVic_BIDA302)
[<img src="https://raw.githubusercontent.com/Bioconductor/BiocStickers/master/events/CSAMA/2017/CSAMA2017.png" height="120"/>](https://github.com/Bioconductor/BiocStickers/tree/master/events/CSAMA/2017)
[<img src="https://jeffreyrstevens.quarto.pub/dpavir/logo/dpavir_hex.png" height="120"/>](https://jeffreyrstevens.quarto.pub/dpavir/)

### Stickers for fun

[<img src="https://github.com/MonkmanMH/EIKIFJB/blob/main/EIKIFJB_sigmar_hex.png" height="120"/>](https://github.com/MonkmanMH/EIKIFJB)
[<img src="https://www.karada-good.net/wp/wp-content/uploads/2017/04/kemono-320x371.png" height="120"/>](https://www.karada-good.net/analyticsr/r-584)

### Stickers for organizations

[<img src="https://shanmdphd.github.io/hex/cryptokor.png" height="120"/>](https://github.com/cryptokor)
[<img src="https://github.com/SocialScienceDataLab/methods-bites-logo/blob/main/DMU-logo.png" height="120"/>](https://www.mzes.uni-mannheim.de/socialsciencedatalab/)
[<img src="https://raw.githubusercontent.com/MEDSL/resources/master/images/medsl.png" height="120"/>](https://github.com/MEDSL/)
[<img src="https://user-images.githubusercontent.com/9893806/36942615-8f9b0640-1f2b-11e8-85eb-6d2cabcfd62f.png" height="120"/>](https://github.com/shinycrypto)
[<img src="https://github.com/slc-rug/slcrug-hexsticker/raw/master/R/slcrug_hex.png" height="120"/>](https://github.com/slc-rug/slcrug-hexsticker)

## Print/order stickers

Sticker designers can make their stickers available via [Sticker
Mule](https://www.stickermule.com/uses/hexagon-stickers).

## Related Tools

- [badger](https://github.com/GuangchuangYu/badger): Query information
  and generate badge for using in README and GitHub Pages.
- [ggimage](https://github.com/GuangchuangYu/ggimage): Supports image
  files and graphic objects to be visualized in ‘ggplot2’ graphic
  system.
- [meme](https://github.com/GuangchuangYu/meme/): Create Meme.
- [shadowtext](https://github.com/GuangchuangYu/shadowtext/): Create
  text grob with background shadow.
