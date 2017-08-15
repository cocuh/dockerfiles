FROM cocuh/arch-yaourt

USER user
RUN yaourt --noconfirm -Syyu && \
    yaourt --noconfirm -S texlive-most texlive-lang noto-fonts noto-fonts-cjk python ghostscript && \
    echo clearn up && \
    yes | yaourt -Scc
