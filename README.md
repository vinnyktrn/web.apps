function calculateSugar() {
    const weight = document.getElementById('weight').value;
    const age = document.getElementById('age').value;
    const fruit = document.getElementById('fruit').value;
    
    if (!weight || !age || !fruit) {
        alert('Silakan isi semua data terlebih dahulu');
        return;
    }

    // Kadar gula per 100 gram buah (dalam gram)
    const sugarContent = {
        apple: 10.39,  // Apel
        banana: 12.23, // Pisang
        orange: 9.35   // Jeruk
    };

    // Menghitung kebutuhan gula harian berdasarkan berat badan dan usia
    const dailySugarNeed = (weight * 0.5) + (age * 0.1);

    // Menghitung jumlah buah yang dibutuhkan untuk memenuhi kebutuhan gula harian
    const sugarInFruit = sugarContent[fruit];
    const fruitNeeded = dailySugarNeed / sugarInFruit;

    const resultDiv = document.getElementById('result');
    resultDiv.innerHTML = `
        <p>Kebutuhan gula harian Anda adalah <strong>${dailySugarNeed.toFixed(2)} gram</strong>.</p>
        <p>Untuk memenuhi kebutuhan tersebut, Anda perlu mengonsumsi sekitar <strong>${fruitNeeded.toFixed(2)} buah ${fruit.charAt(0).toUpperCase() + fruit.slice(1)}</strong>.</p>
    `;
}
