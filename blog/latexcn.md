#如何解决mac下winfonts找不到的问题

找不到的字体是
SimSun SimHei SIMKAI.TTF SIMFANG.TTF

在如下文件中定义(ctex宏包)
/usr/local/texlive/2013/texmf-dist/tex/latex/ctex/fontset/ctex-xecjk-winfonts.def

修复

在windows/fonts中,找到楷体,宋体,仿宋,隶书,幼圆等字体

放到~/Library/Fonts/中

这时候可以识别SimSun和SimHei了
但是,SIMKAI.TTF和SIMFANG.TTF仍然提示找不到,大小写也不行.

直接在上面的.def文件中,注释掉相关行

之后:

\setCJKmainfont[BoldFont={SimHei},ItalicFont={KaiTi}]
  {SimSun}
\setCJKsansfont{SimHei}
\setCJKmonofont{[SIMFANG.TTF]}

\setCJKfamilyfont{zhsong}{SimSun}
\setCJKfamilyfont{zhhei}{SimHei}
%\setCJKfamilyfont{zhkai}{[SIMKAI.TTF]}
%\setCJKfamilyfont{zhfs}{[SIMFANG.TTF]}
% \setCJKfamilyfont{zhli}{LiSu}
% \setCJKfamilyfont{zhyou}{YouYuan}

\newcommand*{\songti}{\CJKfamily{zhsong}} % 宋体
\newcommand*{\heiti}{\CJKfamily{zhhei}}   % 黑体
%\newcommand*{\kaishu}{\CJKfamily{zhkai}}  % 楷书
%\newcommand*{\fangsong}{\CJKfamily{zhfs}} % 仿宋
% \newcommand*{\lishu}{\CJKfamily{zhli}}    % 隶书
% \newcommand*{\youyuan}{\CJKfamily{zhyou}} % 幼圆

\endinput

之前

\setCJKmainfont[BoldFont={SimHei},ItalicFont={[SIMKAI.TTF]}]
  {SimSun}
\setCJKsansfont{SimHei}
\setCJKmonofont{[SIMFANG.TTF]}

\setCJKfamilyfont{zhsong}{SimSun}
\setCJKfamilyfont{zhhei}{SimHei}
\setCJKfamilyfont{zhkai}{[SIMKAI.TTF]}
\setCJKfamilyfont{zhfs}{[SIMFANG.TTF]}
% \setCJKfamilyfont{zhli}{LiSu}
% \setCJKfamilyfont{zhyou}{YouYuan}

\newcommand*{\songti}{\CJKfamily{zhsong}} % 宋体
\newcommand*{\heiti}{\CJKfamily{zhhei}}   % 黑体
\newcommand*{\kaishu}{\CJKfamily{zhkai}}  % 楷书
\newcommand*{\fangsong}{\CJKfamily{zhfs}} % 仿宋
% \newcommand*{\lishu}{\CJKfamily{zhli}}    % 隶书
% \newcommand*{\youyuan}{\CJKfamily{zhyou}} % 幼圆

\endinput
