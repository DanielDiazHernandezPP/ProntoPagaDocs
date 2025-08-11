---
title: prueba
deprecated: false
hidden: true
metadata:
  robots: index
---
export default function TransactionalLimitsTable() {
  return (
    <table style={{ borderCollapse: 'collapse', width: '100%', textAlign: 'left', fontFamily: 'Arial, sans-serif' }}>
      <thead>
        <tr style={{ backgroundColor: '#f04f5b', color: 'white' }}>
          <th style={{ padding: '12px' }}>Banco</th>
          <th style={{ padding: '12px' }}>First Transaction</th>
          <th style={{ padding: '12px' }}>Waiting time ⏳</th>
          <th style={{ padding: '12px' }}>Ongoing Transaction</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td style={{ padding: '12px' }}>
            <img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/Banco_de_Chile_logo.svg" width="24" style={{ verticalAlign: 'middle', marginRight: '8px' }} />
            Banco de Chile
          </td>
          <td>$350.000</td>
          <td>12 Hours</td>
          <td>$2.000.000 / $5.000.000</td>
        </tr>
        <tr>
          <td style={{ padding: '12px' }}>
            <img src="https://upload.wikimedia.org/wikipedia/commons/f/f7/Logo_Ita%C3%BA.svg" width="24" style={{ verticalAlign: 'middle', marginRight: '8px' }} />
            Banco Itaú
          </td>
          <td>$200.000 / $300.000</td>
          <td>24 Hours</td>
          <td>$5.000.000</td>
        </tr>
        <tr>
          <td style={{ padding: '12px' }}>
            <img src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Banco_BCI_logo.svg" width="24" style={{ verticalAlign: 'middle', marginRight: '8px' }} />
            Banco BCI
          </td>
          <td>$250.000 / $600.000</td>
          <td>24 Hours</td>
          <td>$5.000.000 / $7.000.000</td>
        </tr>
        <tr>
          <td style={{ padding: '12px' }}>
            <img src="https://upload.wikimedia.org/wikipedia/commons/4/4a/BancoEstado_logo.svg" width="24" style={{ verticalAlign: 'middle', marginRight: '8px' }} />
            Banco Estado
          </td>
          <td>$100.000 / $250.000</td>
          <td>24 Hours</td>
          <td>$1.000.000 / $5.000.000</td>
        </tr>
        <tr>
          <td style={{ padding: '12px' }}>
            <img src="https://upload.wikimedia.org/wikipedia/commons/5/5f/Banco_Santander_Logotipo.svg"  width="24" style={{ verticalAlign: 'middle', marginRight: '8px' }} />
            Banco Santander
          </td>
          <td>$250.000</td>
          <td>24 Hours</td>
          <td>$5.000.000</td>
        </tr>
        <tr>
          <td style={{ padding: '12px' }}>
            <img src="https://upload.wikimedia.org/wikipedia/commons/d/d1/Banco_Falabella_logo.svg" width="24" style={{ verticalAlign: 'middle', marginRight: '8px' }} />
            Banco Falabella
          </td>
          <td>$200.000</td>
          <td>24 Hours</td>
          <td>$7.000.000</td>
        </tr>
        <tr>
          <td style={{ padding: '12px' }}>
            <img src="https://upload.wikimedia.org/wikipedia/commons/5/59/Banco_Security_logo.svg" width="24" style={{ verticalAlign: 'middle', marginRight: '8px' }} />
            Banco Security
          </td>
          <td>$350.000</td>
          <td>48 Hours</td>
          <td>$2.000.000 / $5.000.000</td>
        </tr>
      </tbody>
    </table>
  );
}

<br />

<Image align="center" width="20px" src="https://files.readme.io/b93f49c82927cb2af650266f65cb7b98b103bd866bad86e68d9ded22ce121c9f-Captura_de_pantalla_2025-08-11_a_las_2.50.26_p._m..png" />