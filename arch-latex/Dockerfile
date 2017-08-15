FROM cocuh/arch-yaourt

USER user
RUN yaourt --noconfirm -Syyu && \
    yaourt --noconfirm -S texlive-most texlive-lang python ghostscript && \
    sudo ln -s /usr/share/fonts/TTF /usr/share/texmf-dist/fonts/truetype && \
    sudo mktexlsr && \
    sudo updmap -sys && \
    echo clearn up && \
    yes | yaourt -Scc
