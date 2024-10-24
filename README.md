# Fish-Classification
It is a project that classifies fish images in the dataset. Detailed explanation is in the code.
# Modelin egitim gecmisi
history = mo_fit.history

# Anahtar isimlerini kontrol ederek grafik cizimi
accuracy = history.get('accuracy', [])
validation_accuracy = history.get('val_accuracy', [])
loss = history.get('loss', [])
validation_loss = history.get('val_loss', [])

# Grafik cizimi
plt.figure(figsize=(17, 7))

# Dogruluk grafigi
plt.subplot(2, 2, 1)
if accuracy and validation_accuracy:
    plt.plot(range(len(accuracy)), accuracy, label='Training Accuracy')
    plt.plot(range(len(validation_accuracy)), validation_accuracy, label='Validation Accuracy')
    plt.title('Accuracy')
    plt.xlabel('Epochs')
    plt.ylabel('Accuracy')
    plt.legend(loc='upper left')
else:
    print("Accuracy veya Validation Accuracy verileri eksik!")

# Kayip grafigi
plt.subplot(2, 2, 2)
if loss and validation_loss:
    plt.plot(range(len(loss)), loss, label='Training Loss')
    plt.plot(range(len(validation_loss)), validation_loss, label='Validation Loss')
    plt.title('Loss')
    plt.xlabel('Epochs')
    plt.ylabel('Loss')
    plt.legend(loc='upper left')
else:
    print("Loss veya Validation Loss verileri eksik!")

plt.tight_layout()
plt.show()
