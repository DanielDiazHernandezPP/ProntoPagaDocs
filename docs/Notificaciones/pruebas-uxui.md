---
title: 'Pruebas UX/UI '
excerpt: 'Ambiente para probar las mejoras que implementará el equipo de UX/IU. '
deprecated: false
hidden: true
metadata:
  robots: index
---
## Button

**Button primary**

<Button variant="primary" text="click" icon="fa-solid fa-arrow-up-right-from-square" href="https://google.com" target="_blank" />

<Button variant="primary" text="Clickeame" icon="fa-solid fa-circle-info" href="https://google.com" />

**Button secondary**

<Button variant="secondary" text="click" icon="fa-solid fa-arrow-up-right-from-square" />

## Guide Card

<Cards>
  <GuideCard icon="fa-solid fa-circle-info" title="Guide Card Title" description="Description number 1." />

  <GuideCard icon="fa-solid fa-circle-info" title="Guide Card Title 2 prueba" description="This is a description of the guide card." />
</Cards>

## Image Card

<Cards>
  <ImageCard imageSrc="https://fastly.picsum.photos/id/102/1200/600.jpg?hmac=QNclXkIUydKOl9ZYpra9E-8Z78ef-xI9KvZoBaUC8KI" imageAlt="Placeholder Image" title="Acepta pagos con tarjeta" description="Acepta pagos con tarjeta online de manera segura." />

  <ImageCard imageSrc="https://fastly.picsum.photos/id/102/1200/600.jpg?hmac=QNclXkIUydKOl9ZYpra9E-8Z78ef-xI9KvZoBaUC8KI" imageAlt="Placeholder Image" title="Acepta pagos con tarjeta" description="Acepta pagos con tarjeta online de manera segura." />

  <ImageCard imageSrc="https://fastly.picsum.photos/id/102/1200/600.jpg?hmac=QNclXkIUydKOl9ZYpra9E-8Z78ef-xI9KvZoBaUC8KI" imageAlt="Placeholder Image" title="Acepta pagos con tarjeta" description="Acepta pagos con tarjeta online de manera segura." />

  <ImageCard imageSrc="https://fastly.picsum.photos/id/102/1200/600.jpg?hmac=QNclXkIUydKOl9ZYpra9E-8Z78ef-xI9KvZoBaUC8KI" imageAlt="Placeholder Image" title="Acepta pagos con tarjeta" description="Acepta pagos con tarjeta online de manera segura." />

  <ImageCard imageSrc="https://fastly.picsum.photos/id/102/1200/600.jpg?hmac=QNclXkIUydKOl9ZYpra9E-8Z78ef-xI9KvZoBaUC8KI" imageAlt="Placeholder Image" title="Acepta pagos con tarjeta" description="Acepta pagos con tarjeta online de manera segura." />
</Cards>

## Code

```javascript
console.log("Hola")
```

<br />

```cplusplus
sadasd
sadas
sadsad
sadasd
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
<div>
    <Button variant="primary" text="click" icon="fa-solid fa-arrow-up-right-from-square" />
    <Button variant="secondary" text="click" icon="fa-solid fa-arrow-up-right-from-square" />
</div>


```

<GuideCard icon="fa-solid fa-circle-info" title="Guide Card Title" description="This is a description of the guide card." />

<Cards columns={4} className="pp-cards--autofit">
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
