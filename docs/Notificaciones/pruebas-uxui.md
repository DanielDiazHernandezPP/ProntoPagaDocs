---
title: 'Pruebas UX/UI '
excerpt: 'Ambiente para probar las mejoras que implementará el equipo de UX/IU. '
deprecated: false
hidden: true
metadata:
  robots: index
---
```
ggg
```

<HTMLBlock>{`
<button>hola</button>
`}</HTMLBlock>

<Button variant="primary" text="click" />

```cplusplus
console
sdad
sdasd
```
```javascript
export const Button = ({
    /* text of the button */
    text,
    /* primary | secondary */
    variant = "primary",
    /* sm | md | lg */
    size = "md",
    /* full width */
    full = false,
    /* disabled state */
    disabled = false,
    /* icon */
    icon = "",
    /* link */
    href = "",
    /* link target */
    target = "_self"
}) => {
    const classes = [
        "pp-btn",
        `pp-btn--${variant}`,
        `pp-btn--${size}`,
        full ? "pp-btn--full" : "",
        disabled ? "is-disabled" : "",
    ].join(" ");

    const Component = href ? "a" : "button";

    return (
        <Component className={classes} disabled={disabled} href={href} target={target}>
            <span className="pp-btn__label">{text}</span>
            {icon ? <i className={`pp-btn__icon ${icon}`} aria-hidden="true" /> : null}
        </Component>
    );
};
```

<br />

<div className="pp-guide-card">
  <div className="pp-guide-card__icon">
    <i className="pp-guide-card__icon--img fa-solid fa-circle-info" aria-hidden="true" />
  </div>

  <div className="pp-guide-card__content">
    <h3 className="pp-guide-card__title">
      Inicio rápido
    </h3>

    <p className="pp-guide-card__description">
      Revisa un resumen de lo que necesitas para empezar a recibir pagos con Prontopaga.
    </p>
  </div>
</div>

<br />

<div className="pp-image-card">
  <div className="pp-image-card__media">
    <img src="https://fastly.picsum.photos/id/102/1200/600.jpg?hmac=QNclXkIUydKOl9ZYpra9E-8Z78ef-xI9KvZoBaUC8KI" alt="imagen" />
  </div>

  <div className="pp-image-card__content">
    <h3 className="pp-image-card__title">
      title
    </h3>

    <p className="pp-image-card__description">
      description
    </p>
  </div>
</div>

<Button variant="secondary" text="click" icon="fa-solid fa-arrow-up-right-from-square" />

<Cards columns={4}>
  <Card title="First Card" href="https://readme.com" icon="fa-home" target="_blank">
    Neque porro quisquam est qui dolorem ipsum quia
  </Card>

  <Card title="Second Card" icon="fa-user">
    *Lorem ipsum dolor sit amet, consectetur adipiscing elit*
  </Card>

  <Card title="Third Card" icon="fa-star">
    > Ut enim ad minim veniam, quis nostrud ullamco
  </Card>

  <Card title="Fourth Card" icon="fa-question">
    **Excepteur sint occaecat cupidatat non proident**
  </Card>
</Cards>
