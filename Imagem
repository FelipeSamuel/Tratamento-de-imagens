from PIL import Image
from PIL import ImageFilter


class Imagem(object):

    def __init__(self, caminho = ''):
        self.__caminho = caminho
        self.__imagem = Image.open(caminho)

    def nitidez(self, raio =  2, percentual = 150, limite = 3):
        self.__imagem = self.__imagem.filter(ImageFilter.UnsharpMask(radius = raio, percent = percentual, threshold = limite))
    
    def desfoque_gaussiano(self, raio = 2):
        self.__imagem = self.__imagem.filter(ImageFilter.GaussianBlur(radius = raio))

    def relevo(self):
        self.__imagem = self.__imagem.filter(ImageFilter.EMBOSS)

    def borrado(self):
        self.__imagem = self.__imagem.filter(ImageFilter.BLUR)

    def detalhe(self):
        self.__imagem = self.__imagem.filter(ImageFilter.DETAIL)

    def suave(self):
        self.__imagem = self.__imagem.filter(ImageFilter.SMOOTH)
    
    def mais_suave(self):
        self.__imagem = self.__imagem.filter(ImageFilter.SMOOTH_MORE)

    def borda_realcada(self):
        self.__imagem = self.__imagem.filter(ImageFilter.EDGE_ENHANCE)

    def borda_mais_realcada(self):
        self.__imagem = self.__imagem.filter(ImageFilter.EDGE_ENHANCE_MORE)
    
    def contorno(self):
        self.__imagem = self.__imagem.filter(ImageFilter.CONTOUR)

    def rotacionar(self, graus = 45):
        self.__imagem = self.__imagem.rotate(graus)

    def redimensionar(self, largura, altura):
        tamanho = largura, altura
        self.__imagem = self.__imagem.resize(tamanho, Image.ANTIALIAS)

    def cortar(self,largura, altura, ponto_inicio = 0, ponto_fim = 0):
        self.__imagem = self.__imagem.crop((ponto_inicio, ponto_fim, largura, altura))


    @property
    def largura(self):
        return self.__imagem.size[0]

    @property
    def altura(self):
        return self.__imagem.size[1]
        
    def salvar(self, nome = ''):
        if nome == '':
            nome = self.__caminho
        self.__imagem.save(nome)
