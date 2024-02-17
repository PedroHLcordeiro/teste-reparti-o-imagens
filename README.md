# teste-reparti-o-imagens
import cv2
import os

def particionar_imagem(imagem_path, output_dir, tamanho_pedaco):
    imagem = cv2.imread(imagem_path)
    altura, largura = imagem.shape[:2]

    for i in range(0, altura, tamanho_pedaco):
        for j in range(0, largura, tamanho_pedaco):
            pedaco = imagem[i:i+tamanho_pedaco, j:j+tamanho_pedaco]
            nome_pedaco = f"pedaco_{i}_{j}.png"
            cv2.imwrite(os.path.join(output_dir, nome_pedaco), pedaco)

# Exemplo de uso
particionar_imagem('sua_imagem.jpg', 'output_directory', 100)
