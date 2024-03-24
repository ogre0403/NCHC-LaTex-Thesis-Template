FROM kjarosh/latex:latest-small

RUN apk update && \
	apk add wget git make


# Force update tlmgr
# https://www.tug.org/texlive/tlmgr.html
RUN wget https://mirror.ctan.org/systems/texlive/tlnet/update-tlmgr-latest.sh -O /tmp/update-tlmgr-latest.sh && \
	chmod +x /tmp/update-tlmgr-latest.sh && \
	/tmp/update-tlmgr-latest.sh && \
	rm /tmp/update-tlmgr-latest.sh

# Change the default repository to Taiwan
RUN tlmgr option repository https://ctan.mirror.twds.com.tw/tex-archive/systems/texlive/tlnet


# Install latexindent in Alpine
# https://latexindentpl.readthedocs.io/en/latest/sec-appendices.html#alpine
RUN tlmgr install latexindent

RUN cd /usr/local/bin && \
    curl -L https://cpanmin.us/ -o cpanm && \
    chmod +x cpanm

RUN cpanm -n App::cpanminus && \
	cpanm -n File::HomeDir	&& \
	cpanm -n Params::ValidationCompiler && \
	cpanm -n YAML::Tiny

# Setup Chinese 
COPY ./edukai-5.0.ttf /usr/share/fonts/edukai-5.0.ttf
COPY ./Times-New-Roman.ttf /usr/share/fonts/Times-New-Roman.ttf

RUN fc-cache -fv && \
	tlmgr install xecjk

# NCHC Thesis Template
RUN tlmgr install titlesec appendix

# Install additional packages
# RUN tlmgr install ieeetran algorithms