# AIButton

AI Buttons initiate actions powered by AI and have a distinct appearance to signal users that the action utilizes AI capabilities.

### Code Examples

#### AIButton

```jsx
import { AIButton } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex justify-content-between w-50">
      <AIButton>Basic Button</AIButton>
      <AIButton appearance="primary">Primary Button</AIButton>
    </div>
  );
}
```


#### AIButton

```jsx
import { AIButton } from '@innovaccer/design-system';

() => {
  return <AIButton>Basic Button</AIButton>;
}
```


#### AIButton

```jsx
import { AIButton } from '@innovaccer/design-system';

() => {
  return <AIButton appearance="primary">Primary Button</AIButton>;
}
```


#### AIButton

```jsx
import { AIButton } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex justify-content-between w-50">
      <AIButton>Basic Button</AIButton>
      <AIButton disabled={true}>Disabled Button</AIButton>
    </div>
  );
}
```


#### AIButton

```jsx
import { AIButton } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex justify-content-between w-50">
      <AIButton appearance="primary">Primary Button</AIButton>
      <AIButton appearance="primary" disabled={true}>
        Disabled Button
      </AIButton>
    </div>
  );
}
```# AIChip

AI Chip, based on Action Chips, enables contextual and dynamic AI actions. It has a distinct appearance to signal users that the action utilizes AI capabilities.

### Code Examples

#### AIChip

```jsx
import { AIChip } from '@innovaccer/design-system';

() => {
  return <AIChip icon="edit_note" label="AI chip" />;
}
```


#### AIChip

```jsx
import { AIChip } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex justify-content-between w-50">
      <AIChip icon="edit_note" label="Default chip" />
      <AIChip icon="edit_note" label="Disabled chip" disabled={true} />
    </div>
  );
}
```# AIIconButton



### Code Examples

#### AIIconButton

```jsx
import { AIIconButton } from '@innovaccer/design-system';

() => {
  return <AIIconButton icon="import_contacts" tooltip="Import Contacts" />;
}
```


#### AIIconButton

```jsx
import { Row, Column, AIIconButton, Text } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column className="d-flex align-items-center flex-column">
        <AIIconButton icon="import_contacts" tooltip="Import Contacts" />
        <Text appearance="subtle" className="mt-6">
          Top
        </Text>
      </Column>
      <Column className="d-flex align-items-center flex-column">
        <AIIconButton icon="edit" position="bottom" tooltip="Edit" />
        <Text appearance="subtle" className="mt-6">
          Bottom
        </Text>
      </Column>
    </Row>
  );
}
```


#### AIIconButton

```jsx
import { Row, Column, AIIconButton, Text } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column className="d-flex align-items-center flex-column">
        <AIIconButton icon="import_contacts" />
        <Text appearance="subtle" className="mt-6">
          Regular
        </Text>
      </Column>
      <Column className="d-flex align-items-center flex-column">
        <AIIconButton icon="import_contacts" size="large" />
        <Text appearance="subtle" className="mt-6">
          Large
        </Text>
      </Column>
    </Row>
  );
}
```


#### AIIconButton

```jsx
import { Row, Column, AIIconButton, Text } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column className="d-flex align-items-center flex-column">
        <AIIconButton icon="import_contacts" tooltip="Import Contacts" />
        <Text appearance="subtle" className="mt-6">
          Default
        </Text>
      </Column>
      <Column className="d-flex align-items-center flex-column">
        <AIIconButton icon="import_contacts" disabled={true} tooltip="Import Contacts" />
        <Text appearance="subtle" className="mt-6">
          Disabled
        </Text>
      </Column>
    </Row>
  );
}
```# AIResponse

AI response is used to deliver information from Sara to the user.

### Code Examples

#### AIResponse

```jsx
import { Sara, AIResponse, Text, Menu } from '@innovaccer/design-system';

() => {
/**
   *
   *  .AIResponse-menu-button {
   *    opacity: var(--opacity-12);
   *  }
   *
   *  .AIResponse-box:hover .AIResponse-menu-button {
   *    opacity: 1;
   *  }
   * 
   *  .AIResponse-box .Menu-Trigger--active {
   *    opacity: 1;
   *  }
   */

  const [selectedList, setSelectedList] = React.useState({
    pin: false,
    like: false,
    dislike: false,
  });

  return (
    <div className="d-flex w-50">
      <Sara />
      <div className="ml-4">
        <AIResponse>
          <AIResponse.Body>
            <Text>Hello, would you like to book an appointment with your cardiologist?</Text>
          </AIResponse.Body>

          <AIResponse.ActionBar>
            <div className="d-flex">
              <AIResponse.Button
                icon="push_pin"
                className="mr-3"
                selected={selectedList.pin}
                onClick={() => setSelectedList({ ...selectedList, pin: !selectedList.pin })}
              >
                Pin
              </AIResponse.Button>
              <AIResponse.Button icon="content_copy">Copy</AIResponse.Button>
            </div>

            <div className="d-flex align-items-center">
              <AIResponse.Button icon="sync" className="mr-3" tooltip="Regenerate" />
              <AIResponse.Button
                icon="thumb_up"
                iconType="outlined"
                className="mr-3"
                tooltip="Good Response"
                selected={selectedList.like && !selectedList.dislike}
                onClick={() => setSelectedList({ ...selectedList, like: !selectedList.like, dislike: false })}
              />
              <AIResponse.Button
                icon="thumb_down"
                iconType="outlined"
                className="mr-3"
                tooltip="Bad Response"
                selected={selectedList.dislike && !selectedList.like}
                onClick={() => setSelectedList({ ...selectedList, dislike: !selectedList.dislike, like: false })}
              />

              <Menu trigger={<Menu.Trigger className="AIResponse-menu-button" appearance="transparent" size="tiny" />}>
                <Menu.List>
                  <Menu.Item>Share</Menu.Item>
                  <Menu.Item>View source</Menu.Item>
                  <Menu.Item>Report a problem</Menu.Item>
                </Menu.List>
              </Menu>
            </div>
          </AIResponse.ActionBar>
        </AIResponse>
        <Text appearance="subtle" size="small" weight="medium">
          1:00 PM
        </Text>
      </div>
    </div>
  );
}
```


#### AIResponse

```jsx
import { Sara, AIResponse, Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex w-25">
      <Sara />
      <div className="ml-4">
        <AIResponse>
          <AIResponse.Body>
            <Text>
              Acute sinusitis causes the spaces inside the nose, known as sinuses, to become inflamed and swollen. Acute
              sinusitis makes it hard for the sinuses to drain. Mucus builds up.
            </Text>
            <img alt="placeholder" src={Image} className="mt-4" />
          </AIResponse.Body>
        </AIResponse>
        <Text appearance="subtle" size="small" weight="medium">
          1:00 PM
        </Text>
      </div>
    </div>
  );
}
```


#### AIResponse

```jsx
import { PlaceholderParagraph, Text, Sara, AIResponse, ChatMessage, Menu } from '@innovaccer/design-system';

() => {
  const ChatMessage = (props) => {
    const { visibleSentences, setVisibleSentences, loading, setLoading } = props;

    const sentences = [
      'Value-based care (VBC) is a healthcare delivery model in which providers, including hospitals and physicians, are paid based on patient health outcomes.',
      'This contrasts with the traditional fee-for-service model, where providers are paid based on the amount of healthcare services they deliver.',
      'The primary goal of VBC is to improve the quality of care provided to patients while reducing costs.',
    ];

    React.useEffect(() => {
      if (loading) {
        const timer = this.window.setTimeout(() => {
          setLoading(false);
          let delay = 0;
          sentences.forEach((sentence) => {
            this.window.setTimeout(() => {
              setVisibleSentences((prev) => [...prev, sentence]);
            }, delay);
            delay += 240;
          });
        }, 1200);
        return () => this.window.clearTimeout(timer);
      }
    }, [loading]);

    const ShowLoaders = () => {
      return (
        <div>
          <PlaceholderParagraph length="large" />
          <PlaceholderParagraph length="medium" />
        </div>
      );
    };

    return (
      <>
        {loading ? (
          <ShowLoaders />
        ) : (
          <div>
            {visibleSentences.map((sentence, index) => (
              <Text key={index} className="AIResponse-text">
                {sentence}{' '}
              </Text>
            ))}
          </div>
        )}
      </>
    );
  };

  const GenerateContent = () => {

    /**
     *
     *  .AIResponse-menu-button {
     *    opacity: var(--opacity-12);
     *  }
     *
     *  .AIResponse-box:hover .AIResponse-menu-button {
     *    opacity: 1;
     *  }
     *
     *  .AIResponse-box .Menu-Trigger--active {
     *    opacity: 1;
     *  }
     *
     *  .AIResponse-text {
     *    animation: fadeIn var(--duration--moderate-02) var(--standard-productive-curve);
     *  }
     *
     */

    const [loading, setLoading] = React.useState(true);
    const [visibleSentences, setVisibleSentences] = React.useState([]);
    const [selectedList, setSelectedList] = React.useState({
      pin: false,
      like: false,
      dislike: false,
    });

    const handleRegenerate = () => {
      setLoading(true);
      setVisibleSentences([]);
    };

    return (
      <div className="d-flex w-50">
        <Sara />
        <div className="ml-4 w-100">
          <AIResponse>
            <AIResponse.Body>
              {
                <ChatMessage
                  loading={loading}
                  setVisibleSentences={setVisibleSentences}
                  visibleSentences={visibleSentences}
                  setLoading={setLoading}
                />
              }
            </AIResponse.Body>

            <AIResponse.ActionBar>
              <div className="d-flex">
                <AIResponse.Button
                  icon="push_pin"
                  className="mr-3"
                  selected={selectedList.pin}
                  onClick={() => setSelectedList({ ...selectedList, pin: !selectedList.pin })}
                >
                  Pin
                </AIResponse.Button>
                <AIResponse.Button icon="content_copy">Copy</AIResponse.Button>
              </div>

              <div className="d-flex align-items-center">
                <AIResponse.Button icon="sync" className="mr-3" tooltip="Regenerate" onClick={handleRegenerate} />
                <AIResponse.Button
                  icon="thumb_up"
                  iconType="outlined"
                  className="mr-3"
                  tooltip="Good Response"
                  selected={selectedList.like && !selectedList.dislike}
                  onClick={() => setSelectedList({ ...selectedList, like: !selectedList.like, dislike: false })}
                />
                <AIResponse.Button
                  icon="thumb_down"
                  iconType="outlined"
                  className="mr-3"
                  tooltip="Bad Response"
                  selected={selectedList.dislike && !selectedList.like}
                  onClick={() => setSelectedList({ ...selectedList, dislike: !selectedList.dislike, like: false })}
                />

                <Menu trigger={<Menu.Trigger className="AIResponse-menu-button" appearance="transparent" size="tiny" />}>
                  <Menu.List>
                    <Menu.Item>Share</Menu.Item>
                    <Menu.Item>View source</Menu.Item>
                    <Menu.Item>Report a problem</Menu.Item>
                  </Menu.List>
                </Menu>
              </div>
            </AIResponse.ActionBar>
          </AIResponse>
          <Text appearance="subtle" size="small" weight="medium">
            1:00 PM
          </Text>
        </div>
      </div>
    );
  }

  return <GenerateContent />
}
```


#### AIResponse

```jsx
import { AIResponse, PlaceholderParagraph } from '@innovaccer/design-system';

() => {
  return (
    <AIResponse className="w-50">
      <PlaceholderParagraph length="large" />
      <PlaceholderParagraph length="medium" />
    </AIResponse>
  );
}
```


#### AIResponse

```jsx
import { Card, CardHeader, Text, Button, Divider, CardBody, SaraSparkle, AIResponse, Menu, Icon, LinkButton, ChipGroup, Textarea } from '@innovaccer/design-system';

() => {

/**
  *  // Define animation classes in style.css file

@keyframes expandForm {
  from {
    height: 0;
    opacity: 0;
  }
  to {
    height: 216px;
    opacity: 1;
  }
}

@keyframes collapseForm {
  from {
    height: 216px;
    opacity: 1;
  }
  to {
    height: 0;
    opacity: 0;
  }
}

.feedback-card-animate {
  animation: fadeIn var(--duration--moderate-02) var(--entrance-productive-curve);
  animation-fill-mode: forwards;
}

.feedback-form-animate--open {
  animation: expandForm var(--duration--moderate-02) var(--entrance-productive-curve);
  animation-fill-mode: forwards;
}

.feedback-form-animate--close {
  animation: collapseForm var(--duration--moderate-02) var(--exit-productive-curve);
  animation-fill-mode: forwards;
}

.feedback-content-animate--open {
  animation: fadeIn var(--duration--moderate-02) var(--entrance-productive-curve);
  animation-fill-mode: forwards;
  animation-delay: var(--duration--moderate-02);
  opacity: 0;
}

.feedback-content-animate--close {
  animation: fadeOut var(--duration--moderate-02) var(--exit-productive-curve);
  animation-fill-mode: forwards;
  opacity: 0;
}

*/

  const [showComment, setShowComment] = React.useState(false);
  const [isFormSubmitted, setIsFormSubmitted] = React.useState(false);
  const [selectedChipList, setSelectedChipList] = React.useState([]);
  const [showClosingAnimation, setShowClosingAnimation] = React.useState(false);
  const [selectedList, setSelectedList] = React.useState({
    like: false,
    dislike: false,
  });

  const positiveChipOptions = [
    { label: 'Accurate', name: '1', type: 'selection', selected: selectedChipList.includes('1') },
    { label: 'Appropriate', name: '2', type: 'selection', selected: selectedChipList.includes('2') },
    { label: 'Easy to understand', name: '3', type: 'selection', selected: selectedChipList.includes('3') },
  ];

  const negativeChipOptions = [
    { label: 'Inaccurate', name: '4', type: 'selection', selected: selectedChipList.includes('4') },
    { label: 'Inappropriate', name: '5', type: 'selection', selected: selectedChipList.includes('5') },
    { label: 'Offensive', name: '6', type: 'selection', selected: selectedChipList.includes('6') },
  ];

  React.useEffect(() => {
    if(!selectedList.like && !selectedList.dislike) {
      setShowComment(false);
    }
  }, [selectedList]);

  const handleChipSelection = (selectedChip) => {
    const name = selectedChip.name;
    if (selectedChipList.includes(name)) {
      const newList = selectedChipList.filter((chipName) => chipName !== name);
      setSelectedChipList(newList);
    } else {
      setSelectedChipList([...selectedChipList, name]);
    }
  };

  const onSubmitClick = () => {
    setIsFormSubmitted(true);
    setShowClosingAnimation(true);
  };

  const cardClassNames = showClosingAnimation ? 'feedback-form-animate--close mt-5 py-4 px-5' : 'feedback-form-animate--open mt-5 py-4 px-5';
  const contentClassNames = showClosingAnimation ? 'feedback-content-animate--close' : 'feedback-content-animate--open';

  const onAnimationEnd = () => {
    if (showClosingAnimation) {
      setShowComment(false);
      setShowClosingAnimation(false);
    }
  };

  return (
    <Card shadow="none" className="w-50 vh-100">
      <CardHeader className="d-flex justify-content-between align-items-center">
        <Text weight="strong" size="regular">
          Smart assist
        </Text>
        <Button appearance="transparent" aria-label="Close" icon="close" />
      </CardHeader>
      <Divider />
      <CardBody className="mt-6">
        <div className="d-flex">
          <SaraSparkle />
          <div className="ml-4">
            <Text weight="strong">Suggest available slots for follow-up appointment with the PCP</Text>

            <AIResponse className="mt-5">
              <AIResponse.Body>
                <Text>It looks like Dr.Smith is available next month on 5th November at 10am, 11am and 2pm EST.</Text>
              </AIResponse.Body>

              <AIResponse.ActionBar className="justify-content-end">
                <div className="d-flex align-items-center">
                  <AIResponse.Button
                    icon="sync"
                    className="mr-3"
                    tooltip="Regenerate"
                    onClick={() => {
                      setSelectedList({ ...selectedList, like: false, dislike: false });
                      setShowComment(false);
                      setIsFormSubmitted(false);
                    }}
                  />
                  <AIResponse.Button
                    icon="thumb_up"
                    iconType="outlined"
                    className="mr-3"
                    tooltip="Good Response"
                    selected={selectedList.like && !selectedList.dislike}
                    onClick={() => setSelectedList({ ...selectedList, like: !selectedList.like, dislike: false })}
                  />
                  <AIResponse.Button
                    icon="thumb_down"
                    iconType="outlined"
                    className="mr-3"
                    tooltip="Bad Response"
                    selected={selectedList.dislike && !selectedList.like}
                    onClick={() => setSelectedList({ ...selectedList, dislike: !selectedList.dislike, like: false })}
                  />

                  <Menu
                    trigger={<Menu.Trigger className="AIResponse-menu-button" appearance="transparent" size="tiny" />}
                  >
                    <Menu.List>
                      <Menu.Item>Share</Menu.Item>
                      <Menu.Item>View source</Menu.Item>
                      <Menu.Item>Report a problem</Menu.Item>
                    </Menu.List>
                  </Menu>
                </div>
              </AIResponse.ActionBar>
            </AIResponse>
            <Text appearance="subtle" size="small" weight="medium">
              1:00 PM
            </Text>

            {(selectedList.like || selectedList.dislike) && !showComment && (
              <Card shadow="none" className="mt-5">
                <div className="d-flex justify-content-between py-4 px-5 align-items-center feedback-card-animate">
                  <Text weight="medium">Thanks for sharing your feedback</Text>
                  <div className="d-flex align-items-center">
                    {isFormSubmitted ? (
                      <Icon name="check_circle" size={16} appearance="success" />
                    ) : (
                      <LinkButton onClick={() => setShowComment(true)}>Tell us more</LinkButton>
                    )}
                  </div>
                </div>
              </Card>
            )}

            {showComment && (selectedList.like || selectedList.dislike) &&  (
              <Card
                shadow="none"
                className={cardClassNames}
                onAnimationEnd={onAnimationEnd}
              >
                <div className={contentClassNames}>
                  <Text weight="medium">Tell us more</Text>
                  <div className="mt-7">
                    <ChipGroup
                      list={selectedList.like ? positiveChipOptions : negativeChipOptions}
                      onClick={handleChipSelection}
                    />

                    <Textarea
                      aria-labelledby="Textarea"
                      name="Textarea"
                      placeholder="Additional comments"
                      resize={false}
                      rows={3}
                      className="mt-5"
                    />

                    <div className="d-flex justify-content-end mt-6">
                      <Button className="mr-4" size="tiny" onClick={() => setShowClosingAnimation(true)}>
                        Skip
                      </Button>
                      <Button
                        appearance="primary"
                        size="tiny"
                        onClick={onSubmitClick}
                        disabled={selectedChipList.length <= 0}
                      >
                        Submit
                      </Button>
                    </div>
                  </div>
                </div>
              </Card>
            )}
          </div>
        </div>
      </CardBody>
    </Card>
  );
}
```# ActionCard



### Code Examples

#### Action Card

```jsx
import { ActionCard, Icon, Text } from '@innovaccer/design-system';

() => {
  return (
    <ActionCard className="w-25">
      <div className="d-flex flex-column align-items-center justify-content-center p-6 text-align-center">
        <Icon name="store" size={24} className="mb-4" />
        <Text weight="strong" className="mb-2">
          Marketplace
        </Text>
        <Text appearance="subtle">Explore and purchase apps and add-ons</Text>
      </div>
    </ActionCard>
  );
}
```


#### Action Card

```jsx
import { ActionCard, Icon, Text } from '@innovaccer/design-system';

() => {
  const cardList = [
    {
      icon: 'api',
      title: 'API portal',
      description: 'Access and test out application APIs',
    },
    {
      icon: 'preview',
      title: 'App simulator',
      description: 'Envision and test the apps that you want to integrate with Innovaccer',
    },
    {
      icon: 'widgets',
      title: 'App distribution',
      description: 'Publish and monetize your apps and add-ons',
    },
    {
      icon: 'store',
      title: 'Marketplace',
      description: 'Explore and purchase apps and add-ons',
    },
  ];

  return (
    <div className="d-flex">
      {cardList.map((cardItem, key) => {
        const { icon, title, description } = cardItem;
        return (
          <ActionCard key={key} className="mr-6">
            <div className="d-flex flex-column align-items-center justify-content-center p-6 text-align-center">
              <Icon name={icon} size={24} className="mb-4" />
              {title && <Text weight="strong" className="mb-2">{title}</Text>}
              {description && <Text appearance="subtle">{description}</Text>}
            </div>
          </ActionCard>
        );
      })}
    </div>
  );
}
```


#### Action Card

```jsx
import { Text, ActionCard, Icon } from '@innovaccer/design-system';

() => {
  return (
    <div>
      <Text weight="strong">Center Content Alignment:</Text>
      <ActionCard className="w-25 mb-8 mt-6">
        <div className="d-flex flex-column align-items-center justify-content-center p-6 text-align-center">
          <Icon name="store" size={24} className="mb-4" />
          <Text weight="strong" className="mb-2">
            Marketplace
          </Text>
          <Text appearance="subtle">Explore and purchase apps and add-ons</Text>
        </div>
      </ActionCard>

      <Text weight="strong">Left Content Alignment:</Text>
      <ActionCard className="w-25 mt-6">
        <div className="d-flex justify-content-center p-6 text-align-start">
          <Icon name="store" size={24} className="mr-5" />
          <div>
            <Text weight="strong">Marketplace</Text>
            <br />
            <Text className="pt-2" appearance="subtle">
              Explore and purchase apps and add-ons
            </Text>
          </div>
        </div>
      </ActionCard>
    </div>
  );
}
```


#### Action Card

```jsx
import { Text, ActionCard, Icon } from '@innovaccer/design-system';

() => {
  return (
    <div>
      <Text weight="strong">Default:</Text>
      <ActionCard className="w-25 mb-8 mt-6">
        <div className="d-flex justify-content-center p-6 text-align-start">
          <Icon name="store" size={24} className="mr-5" />
          <div>
            <Text weight="strong">Marketplace</Text>
            <br />
            <Text className="pt-2" appearance="subtle">
              Explore and purchase apps and add-ons
            </Text>
          </div>
        </div>
      </ActionCard>

      <Text weight="strong">Disabled:</Text>
      <ActionCard disabled={true} className="w-25 mt-6">
        <div className="d-flex justify-content-center p-6 text-align-start">
          <Icon name="store" size={24} className="mr-5" />
          <div>
            <Text weight="strong">Marketplace</Text>
            <br />
            <Text className="pt-2" appearance="subtle">
              Explore and purchase apps and add-ons
            </Text>
          </div>
        </div>
      </ActionCard>
    </div>
  );
}
```# Avatar

Avatar is used to identify an entity through display pictures, icons or their initials.

### Code Examples

#### Components Avatar Avatar All

```jsx
import { Avatar } from '@innovaccer/design-system';

() => {
  const appearance = 'primary';
  const size = 'tiny';
  const withTooltip = true;
  const children = '';
  const firstName = 'John';
  const lastName = 'Doe';

  const options = {
    appearance,
    withTooltip,
    size,
    firstName,
    lastName,
  };

  return <Avatar {...options}>{children}</Avatar>;
}
```


#### Avatar

```jsx
import { Avatar } from '@innovaccer/design-system';

() => <Avatar firstName="John" lastName="Doe" appearance="primary" />
```


#### Avatar

```jsx
import { Row, Column, Text, Avatar } from '@innovaccer/design-system';

() => {
  const weight = 'strong';

  return (
    <Row className="w-50">
      <Column>
        <Text weight={weight}>Active</Text>
        <br />
        <br />
        <Avatar firstName="John" lastName="Doe" presence="active" />
      </Column>
      <Column>
        <Text weight={weight}>Away</Text>
        <br />
        <br />
        <Avatar firstName="John" lastName="Doe" presence="away" />
      </Column>
    </Row>
  );
}
```


#### Avatar

```jsx
import { Row, Column, Avatar, Text } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column className="d-flex align-items-center flex-column">
        <Avatar appearance="primary" firstName="John" lastName="Doe" />
        <Text appearance="subtle" className="mt-6">
          Default
        </Text>
      </Column>
      <Column className="d-flex align-items-center flex-column">
        <Avatar appearance="primary" firstName="John" lastName="Doe" disabled={true} tooltipSuffix="(Deactivated)" />
        <Text appearance="subtle" className="mt-6">
          Disabled
        </Text>
      </Column>
    </Row>
  );
}
```


#### Avatar

```jsx
import { Avatar, Tooltip, Icon } from '@innovaccer/design-system';

() => {
  return (
    <Avatar
      lastName="Doe"
      firstName="John"
      appearance="primary"
      status={
        <Tooltip tooltip="Verified" position="top">
          <Icon name="done" size={10} appearance="white" className="p-1 bg-success" />
        </Tooltip>
      }
    />
  );
}
```


#### Avatar

```jsx
import { Avatar, Tooltip } from '@innovaccer/design-system';

() => {
  return (
    <Avatar
      firstName="Tom"
      lastName="Yusuf"
      appearance="accent1"
      status={
        <Tooltip tooltip="DND" position="top">
          <img width="14px" alt="DND" src={StatusImage} />
        </Tooltip>
      }
    />
  );
}
```


#### Avatar

```jsx
import { Text, Avatar } from '@innovaccer/design-system';

() => {
  const weight = 'strong';

  const appearances = [
    'primary',
    'secondary',
    'alert',
    'warning',
    'success',
    'accent1',
    'accent2',
    'accent3',
    'accent4',
  ];

  return (
    <div className="d-flex">
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="mr-9">
            <Text weight={weight}>{appear.charAt(0).toUpperCase() + appear.slice(1)}</Text>
            <br />
            <br />
            <Avatar firstName="John" lastName="Doe" appearance={appear} />
          </div>
        );
      })}
    </div>
  );
}
```


#### Avatar

```jsx
import { Row, Column, Text, Avatar } from '@innovaccer/design-system';

() => {
  const weight = 'strong';

  return (
    <Row className="w-50">
      <Column>
        <Text weight={weight}>Round</Text>
        <br />
        <br />
        <Avatar appearance="accent2" firstName="John" lastName="Doe" />
      </Column>
      <Column>
        <Text weight={weight}>Square</Text>
        <br />
        <br />
        <Avatar appearance="accent2" firstName="John" lastName="Doe" shape="square" />
      </Column>
    </Row>
  );
}
```


#### Avatar

```jsx
import { Row, Column, Text, Avatar } from '@innovaccer/design-system';

() => {
  return (
    <div>
      <Row>
        <Column>
          <Text weight="strong">Regular</Text>
          <div className="d-flex mt-7">
            <Avatar firstName="John" lastName="Doe" className="mr-8" />
            <Avatar appearance="accent4" firstName="John" lastName="Doe" shape="square" />
          </div>
        </Column>
        <Column>
          <Text weight="strong">Tiny</Text>
          <div className="d-flex mt-7">
            <Avatar firstName="John" lastName="Doe" size="tiny" className="mr-8" />
            <Avatar appearance="accent4" firstName="John" lastName="Doe" shape="square" size="tiny" />
          </div>
        </Column>
      </Row>
    </div>
  );
}
```


#### Components Avatar Avatar With Icon

```jsx
import { Avatar } from '@innovaccer/design-system';

() => {
  const appearance = 'primary';
  const withTooltip = true;
  const firstName = 'Innovaccer';
  const lastName = 'Bot';

  const options = {
    appearance,
    withTooltip,
    firstName,
    lastName,
  };

  return (
    <Avatar {...options} shape="square">
      <Avatar.Icon name="smart_toy" />
    </Avatar>
  );
}
```


#### Components Avatar Avatar With Image

```jsx
import { Avatar } from '@innovaccer/design-system';

() => {
  const appearance = 'secondary';
  const withTooltip = true;
  const firstName = 'Innovaccer';
  const lastName = 'logo';

  const options = {
    appearance,
    withTooltip,
    firstName,
    lastName,
  };

  return (
    <Avatar {...options}>
      <Avatar.Image src="https://design.innovaccer.com/images/withoutType.png" />
    </Avatar>
  );
}
```


#### Components Avatar Avatar With Suffix

```jsx
import { Avatar } from '@innovaccer/design-system';

() => {
  const withTooltip = true;
  const firstName = 'John';
  const lastName = 'Doe';
  const tooltipSuffix = '(Deactivated)';
  const disabled = true;

  const options = {
    withTooltip,
    firstName,
    lastName,
    disabled,
    tooltipSuffix,
  };

  return <Avatar {...options} />;
}
```


#### Components Avatar Avatar With Svg

```jsx
import { Avatar } from '@innovaccer/design-system';

() => {
  const withTooltip = true;
  const firstName = 'John';
  const lastName = 'Doe';

  const options = {
    withTooltip,
    firstName,
    lastName,
  };

  return (
    <Avatar {...options}>
      <Avatar.Image>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="black" width="18px" height="18px">
          <path d="M12 14c1.66 0 2.99-1.34 2.99-3L15 5c0-1.66-1.34-3-3-3S9 3.34 9 5v6c0 1.66 1.34 3 3 3zm5.3-3c0 3-2.54 5.1-5.3 5.1S6.7 14 6.7 11H5c0 3.41 2.72 6.23 6 6.72V21h2v-3.28c3.28-.48 6-3.3 6-6.72h-1.7z" />
          <path d="M0 0h24v24H0z" fill="none" />
        </svg>
      </Avatar.Image>
    </Avatar>
  );
}
```# AvatarGroup

Avatar group displays a group of avatars stacked together.

### Code Examples

#### Components Avatar AvatarGroup All

```jsx
import { Avatar, AvatarGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler'
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
      icon: <Avatar.Icon name="person" />
    },
    {
      firstName: 'Anuradha',
      lastName: 'Aggarwal',
      image: <Avatar.Image src="https://design.innovaccer.com/images/avatar2.jpeg" />,
    },
    {
      firstName: 'Monica',
      lastName: 'Geller'
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
  ];
  return <AvatarGroup list={list} popoverOptions={{ position: 'bottom', withSearch: true, on: 'click', searchPlaceholder: 'Search User',}} />;
}
```


#### Components Avatar AvatarGroup Overflow Behavior

```jsx
import { Text, AvatarGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler'
    },
    {
      firstName: 'Monica',
      lastName: 'Geller'
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
    },
    {
      firstName: 'Walter Paxton',
      lastName: 'Wheeler'
    },
  ];

  return (
    <div className="d-flex">
      <div className="flex-column mr-9 ">
        <Text weight="strong">Dynamic Width (Recommended)</Text>
        <div className="mt-4">
          <AvatarGroup list={list} popoverOptions={{ width: 200 }} />
        </div>
      </div>
      <div className="flex-column">
        <Text weight="strong">Truncate</Text>
        <div className="mt-4">
          <AvatarGroup list={list} />
        </div>
      </div>
    </div>
  );
}
```


#### Components Avatar AvatarGroup Variants Border Color

```jsx
import { AvatarGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler'
    },
    {
      firstName: 'Monica',
      lastName: 'Geller'
    },
  ];

  const popoverOptions = { on: 'hover' };

  return (
    <div className='d-flex justify-content-between align-items-center w-75'>
      <AvatarGroup size="regular" list={list.slice(0, 4)} popoverOptions={popoverOptions}/>
      <AvatarGroup size="regular" borderColor="var(--secondary-lightest)" 
        className='bg-secondary-lightest p-4' list={list.slice(0, 4)} popoverOptions={popoverOptions}/>
      <AvatarGroup size="tiny" list={list.slice(0, 4)} popoverOptions={popoverOptions}/>
      <AvatarGroup size="tiny" borderColor="var(--secondary-lightest)" list={list.slice(0, 4)} 
        className='bg-secondary-lightest p-4' popoverOptions={popoverOptions}/>
    </div>
  );
}
```


#### Components Avatar AvatarGroup Variants Custom Popover

```jsx
import { Avatar, Text, AvatarGroup } from '@innovaccer/design-system';

/*
// style.css
.UserAvatars-popover {
    max-height: var(--spacing-7);
}
*/

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler'
    },
    {
      firstName: 'Monica',
      lastName: 'Geller'
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler'
    },
  ];

  const popperRenderer = (list) => {
    const AvatarList = list.map((avatar, index) => {
      const { firstName, lastName, appearance } = avatar;

      return (
        <div className="d-flex align-items-center mr-4 mb-4" key={index}>
          <Avatar
            firstName={firstName}
            lastName={lastName}
            appearance={appearance}
            className="mr-4"
            withTooltip={false}
          />
          <Text>{`${firstName} ${lastName}`}</Text>
        </div>
      )
    });

    return (
      <div className="overflow-auto py-4 px-6 UserAvatars-popover">
        {AvatarList}
      </div>
    )
  };

  return (
    <AvatarGroup
      list={list}
      popoverOptions={{ dark: false, popperRenderer }}
    />
  );
}
```


#### Components Avatar AvatarGroup Variants Size

```jsx
import { Text, AvatarGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler'
    },
    {
      firstName: 'Monica',
      lastName: 'Geller'
    },
  ];

  const popoverOptions = { on: 'hover' };

  return (
    <div className="d-flex">
      <div className="flex-column mr-9">
        <Text weight="strong">Regular</Text>
        <div className="mt-4">
          <AvatarGroup size="regular" list={list.slice(0, 4)} popoverOptions={popoverOptions}/>
        </div>
      </div>
      <div className="flex-column">
        <Text weight="strong">Tiny</Text>
        <div className="mt-4">
          <AvatarGroup size="tiny" list={list.slice(0, 4)} popoverOptions={popoverOptions}/>
        </div>
      </div>
    </div>
  );
}
```


#### Components Avatar AvatarGroup Variants State

```jsx
import { Text, AvatarGroup } from '@innovaccer/design-system';

() => {
  const popoverOptions = { on: 'hover' };

  return (
    <div className="d-flex">
      <div className="flex-column mr-9 ">
        <Text weight="strong">Default</Text>
        <div className="mt-4">
          <AvatarGroup size="regular" list={list.slice(0, 4)} popoverOptions={popoverOptions} />
        </div>
      </div>
      <div className="flex-column">
        <Text weight="strong">Disabled</Text>
        <div className="mt-4">
          <AvatarGroup list={disabledList.slice(0, 4)} popoverOptions={popoverOptions} />
        </div>
      </div>
    </div>
  );
}
```


#### Components Avatar AvatarGroup Variants Trigger

```jsx
import { Text, AvatarGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler'
    },
    {
      firstName: 'Monica',
      lastName: 'Geller'
    },
  ];

  return (
    <div className="d-flex">
      <div className="flex-column mr-9 ">
        <Text weight="strong">Hover</Text>
        <div className="mt-4">
          <AvatarGroup list={list.slice(0, 4)} popoverOptions={{ on: 'hover' }} />
        </div>
      </div>
      <div className="flex-column">
        <Text weight="strong">Click</Text>
        <div className="mt-4">
          <AvatarGroup list={list.slice(0, 4)} popoverOptions={{ on: 'click' }} />
        </div>
      </div>
    </div>
  );
}
```


#### Components Avatar AvatarGroup With Icon

```jsx
import { Avatar, AvatarGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
      icon: <Avatar.Icon name="person" />
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
      icon: <Avatar.Icon name="person" />
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
      icon: <Avatar.Icon name="person" />
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
      icon: <Avatar.Icon name="person" />
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
      icon: <Avatar.Icon name="person" />
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
      icon: <Avatar.Icon name="person" />
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler',
      icon: <Avatar.Icon name="person" />
    },
  ];
  return <AvatarGroup list={list} />;
}
```


#### Components Avatar AvatarGroup With Image

```jsx
import { Avatar, AvatarGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'Satyam',
      lastName: 'Yadav',
      image: <Avatar.Image src="https://design.innovaccer.com/images/avatar1.png" />,
    },
    {
      firstName: 'Anuradha',
      lastName: 'Aggarwal',
      image: <Avatar.Image src="https://design.innovaccer.com/images/avatar2.jpeg" />,
    },
    {
      firstName: 'Shivaansh',
      lastName: 'Sharma',
      image: <Avatar.Image src="https://design.innovaccer.com/images/github.png" />,
    },
  ];
  return <AvatarGroup list={list} />;

}
```# AvatarSelection



### Code Examples

#### Components Avatar AvatarSelection All

```jsx
import { Avatar, AvatarSelection } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
      selected: true,
    },
    {
      firstName: 'Anuradha',
      lastName: 'Aggarwal',
      image: <Avatar.Image src="https://design.innovaccer.com/images/avatar2.jpeg" />,
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
      icon: <Avatar.Icon name="person" />,
    },
    {
      firstName: 'Satyam',
      lastName: 'Yadav',
      selected: true,
      image: <Avatar.Image src="https://design.innovaccer.com/images/avatar1.png" />,
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler',
      selected: true,
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
  ];

  const onSelectHandler = (props) => {
    console.log('props', props);
  };

  const searchComparator = (searchValue, data) => {
    if (searchValue === '') {
      return true;
    }
    return data.firstName.toLowerCase().includes(searchValue.toLowerCase());
  };

  return (
    <AvatarSelection
      list={list}
      withSearch={true}
      onSelect={onSelectHandler}
      searchPlaceholder="Search User"
      searchComparator={searchComparator}
    />
  );
}
```


#### Components Avatar AvatarSelection Custom

```jsx
import { Tooltip, AvatarSelection, Checkbox } from '@innovaccer/design-system';

() => {

  /*
    .AvatarSelection-wrapper {
      width: var(--spacing-8);
    }
  */
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
      selected: true,
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
    {
      firstName: 'Thom',
      lastName: 'Yorke',
      email: 'thom12@gmail.com',
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
    },
    {
      firstName: 'Walter Harry Paxton',
      lastName: 'Wheeler',
      selected: true,
    },
  ];

  const [avatarList, setAvatarList] = React.useState(list);
  const [searchList, setSearchList] = React.useState(list.slice(5, list.length));
  const [selectedItems, setSelectedItems] = React.useState([
    {
      firstName: 'John',
      lastName: 'Doe',
      iconOptions: {
        name: 'places',
        type: 'outlined',
      },
      selected: true,
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler',
      selected: true,
    },
  ]);

  React.useEffect(() => {
    const updatedList = avatarList.map((avatar) => {
      if (selectedItems.includes(avatar)) {
        avatar.selected = true;
      } else {
        avatar.selected = false;
      }
      return avatar;
    });
    setAvatarList(updatedList);
  }, [selectedItems]);

  const onSearchHandler = (event) => {
    const searchValue = event.target.value.toLowerCase();
    const popoverList = avatarList.slice(5, avatarList.length);

    const list = popoverList.filter((avatarData) => {
      return avatarData.firstName.toLowerCase().includes(searchValue.toLowerCase());
    });

    setSearchList(list);
  };

  const onSelectHandler = (list) => {
    setSelectedItems(list);
  };

  const AvatarSelectionItem = (props) => {
    const { avatarData, isSelected } = props;
    const [showTooltip, setShowTooltip] = React.useState(false);
    const elementRef = React.useRef(null);

    const { firstName = '', lastName = '', email } = avatarData;
    const name = `${firstName} ${lastName}`;

    return (
      <Tooltip showOnTruncation={true} tooltip={name} elementRef={elementRef} open={showTooltip}>
        <AvatarSelection.Option
          value={avatarData}
          className="d-flex align-items-center"
          onFocus={() => {
            setShowTooltip(true);
          }}
          onBlur={() => {
            setShowTooltip(false);
          }}
        >
          <Checkbox
            key={isSelected}
            checked={isSelected}
            label={name}
            size="regular"
            helpText={email}
            labelRef={elementRef}
            className="w-100"
          />
        </AvatarSelection.Option>
      </Tooltip>
    );
  };

  return (
    <AvatarSelection size="tiny" list={avatarList} onSelect={onSelectHandler}>
      <div className="AvatarSelection-wrapper">
        <AvatarSelection.Input placeholder="Search user" onChange={onSearchHandler} />

        {searchList.length === 0 && (
          <AvatarSelection.EmptyState
            title="No users found"
            description="Try modifying your search to find what you are looking for."
          />
        )}

        <AvatarSelection.List>
          {searchList.map((avatarData, index) => {
            const isSelected = selectedItems.find((item) => item.firstName === avatarData.firstName);

            return <AvatarSelectionItem key={index} avatarData={avatarData} isSelected={isSelected} />;
          })}
        </AvatarSelection.List>
      </div>
    </AvatarSelection>
  );
}
```


#### Components Avatar AvatarSelection List Item Size

```jsx
import { Label, AvatarSelection, Checkbox, Avatar, Text } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
      selected: true,
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
    {
      firstName: 'Thom',
      lastName: 'Yorke',
      email: 'thomyorke12@gmail.com'
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler',
      selected: true,
    },
  ];

  const listSize = ['standard', 'compressed', 'tight'];
  const [avatarList, setAvatarList] = React.useState(list);
  const [searchList, setSearchList] = React.useState(list.slice(5, list.length));
  const [selectedItems, setSelectedItems] = React.useState([
    {
      firstName: 'John',
      lastName: 'Doe',
      selected: true,
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler',
      selected: true,
    },
  ]);

  React.useEffect(() => {
    const updatedList = avatarList.map((avatar) => {
      if (selectedItems.includes(avatar)) {
        avatar.selected = true;
      } else {
        avatar.selected = false;
      }
      return avatar;
    });
    setAvatarList(updatedList);
  }, [selectedItems]);

  const onSearchHandler = (event) => {
    const searchValue = event.target.value.toLowerCase();
    const popoverList = avatarList.slice(5, avatarList.length);

    const list = popoverList.filter((avatarData) => {
      return avatarData.firstName.toLowerCase().includes(searchValue.toLowerCase());
    });

    setSearchList(list);
  };

  const onSelectHandler = (list) => {
    setSelectedItems(list);
  };

  return (
    <div>
      {listSize.map((size, index) => {
        return (
          <div key={index} className="mb-8 w-25">
            <Label htmlFor={size} withInput={true}>
              {size.charAt(0).toUpperCase() + size.slice(1)}
            </Label>
            <br />
            <AvatarSelection size="tiny" list={avatarList} onSelect={onSelectHandler}>
              <AvatarSelection.Input placeholder="Search user" onChange={onSearchHandler} />

              {searchList.length === 0 && (
                <AvatarSelection.EmptyState
                  title="No users found"
                  description="Try modifying your search to find what you are looking for."
                />
              )}

              <AvatarSelection.List size={size}>
                {searchList.map((avatarData, index) => {
                  const { firstName = '', lastName = '' } = avatarData;
                  const name = `${firstName} ${lastName}`;

                  const isSelected = selectedItems.find((item) => item.firstName === avatarData.firstName);

                  return (
                    <AvatarSelection.Option key={index} value={avatarData} className="d-flex align-items-center">
                      <Checkbox
                        key={isSelected}
                        defaultChecked={isSelected}
                        checked={isSelected}
                        size="regular"
                        tabIndex={-1}
                      />
                      <Avatar {...avatarData} className="ml-3 mr-4" withTooltip={false} />
                      <Text className="ellipsis--noWrap">{name}</Text>
                    </AvatarSelection.Option>
                  );
                })}
              </AvatarSelection.List>
            </AvatarSelection>
          </div>
        );
      })}
    </div>
  );
}
```


#### Components Avatar AvatarSelection States

```jsx
import { Avatar, Text, AvatarSelection } from '@innovaccer/design-system';

() => {
  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
      selected: true,
    },
    {
      firstName: 'Anuradha',
      lastName: 'Aggarwal',
      image: <Avatar.Image src="https://design.innovaccer.com/images/avatar2.jpeg" />,
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler',
      selected: true,
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
    },
    {
      firstName: 'Walter',
      lastName: 'Paxton',
      selected: true,
    },
  ];

  const disabledList = [
    {
      firstName: 'John',
      lastName: 'Doe',
      selected: true,
      disabled: true,
      tooltipSuffix: '(Deactivated)',
    },
    {
      firstName: 'Anuradha',
      lastName: 'Aggarwal',
      image: <Avatar.Image src="https://design.innovaccer.com/images/avatar2.jpeg" />,
      disabled: true,
      tooltipSuffix: '(Deactivated)',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler',
      selected: true,
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
      disabled: true,
      tooltipSuffix: '(Deactivated)',
    },
    {
      firstName: 'Walter',
      lastName: 'Paxton',
      selected: true,
    },
  ];

  const onSelectHandler = (props) => {
    action('props', props)();
  };

  const searchComparator = (searchValue, data) => {
    if (searchValue === '') {
      return true;
    }
    return data.firstName.toLowerCase().includes(searchValue.toLowerCase());
  };

  return (
    <div className="d-flex">
      <div className="flex-column mr-9">
        <Text weight="strong">Default</Text>
        <div className="mt-7">
          <AvatarSelection
            list={list}
            withSearch={true}
            onSelect={onSelectHandler}
            searchPlaceholder="Search User"
            searchComparator={searchComparator}
          />
        </div>
      </div>
      <div className="flex-column">
        <Text weight="strong">Disabled</Text>
        <div className="mt-7">
          <AvatarSelection
            list={disabledList}
            withSearch={true}
            onSelect={onSelectHandler}
            searchPlaceholder="Search User"
            searchComparator={searchComparator}
          />
        </div>
      </div>
    </div>
  );
}
```# Backdrop



### Code Examples

#### Components Backdrop All

```jsx
import { Button, Backdrop } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onKeyDown = (event) => {
    if (event.key === 'Escape') {
      setOpen(false);
    }
  };

  return (
    <div onKeyDown={onKeyDown}>
      <Button onClick={() => setOpen(true)} appearance="primary">
        Trigger Backdrop
      </Button>
      <div onClick={() => setOpen(false)}>
        <Backdrop open={open} />
      </div>
    </div>
  );
}
```# Badge



### Code Examples

#### Components Badge All

```jsx
import { Badge } from '@innovaccer/design-system';

() => {
  return <Badge>Approved</Badge>;
}
```


#### Badge

```jsx
import { Badge } from '@innovaccer/design-system';

() => {
  const appearances = [
    'primary',
    'secondary',
    'alert',
    'warning',
    'success',
    'accent1',
    'accent2',
    'accent3',
    'accent4',
  ];

  return (
    <div className="d-flex justify-content-between">
      {appearances.map((appear, ind) => {
        return (
          <Badge key={ind} appearance={appear}>
            {appear}
          </Badge>
        );
      })}
    </div>
  );
}
```


#### Components Badge Solid Warning

```jsx
import { Badge } from '@innovaccer/design-system';

() => {
  return <Badge appearance="warning">Pending</Badge>;
}
```


#### Badge

```jsx
import { Badge } from '@innovaccer/design-system';

() => {
  const appearances = [
    'primary',
    'secondary',
    'alert',
    'warning',
    'success',
    'accent1',
    'accent2',
    'accent3',
    'accent4',
  ];

  return (
    <div className="d-flex justify-content-between">
      {appearances.map((appear, ind) => {
        return (
          <Badge key={ind} appearance={appear} subtle={true}>
            {appear}
          </Badge>
        );
      })}
    </div>
  );
}
```


#### Components Badge Subtle Warning

```jsx
import { Badge } from '@innovaccer/design-system';

() => {
  return (
    <Badge appearance="warning" subtle={true}>
      Pending
    </Badge>
  );
}
```# Breadcrumbs

Breadcrumbs indicate the path of a record and help the users to navigate back to the parent record.

### Code Examples

#### Components Breadcrumbs Label Truncate

```jsx
import { Breadcrumbs, PageHeader } from '@innovaccer/design-system';

() => {
  const breadcrumbs = (
    <Breadcrumbs
      list={[
        {
          label: 'eCQM Performance year 2022',
          link: '/eCQM',
        },
        {
          label: 'Report 1',
          link: '/report1',
        },
      ]}
      onClick={link => console.log(`on-click: ${link}`)}
      showTooltip={true}
    />
  );

  return (
    <div className="py-6 bg-secondary-lightest">
      <PageHeader title="eCQM Performance year 2022" breadcrumbs={breadcrumbs} />
    </div>
  );
}
```


#### Components Breadcrumbs Less Than 4 Levels

```jsx
import { Breadcrumbs } from '@innovaccer/design-system';

() => {
  const list = [
    {
      label: 'Level 0',
      link: '/level0'
    },
    {
      label: 'Level 1',
      link: '/level1'
    },
    {
      label: 'Level 2',
      link: '/level2'
    },
    {
      label: 'Level 3',
      link: '/level3'
    }
  ];

  return (
    <div className="bg-secondary-lightest">
      <Breadcrumbs
        list={list}
        onClick={link => console.log(`on-click: ${link}`)}
      />
    </div>
  );
}
```


#### Components Breadcrumbs More Than 4 Levels

```jsx
import { Breadcrumbs } from '@innovaccer/design-system';

() => {
  const list = [
    {
      label: 'Level 0',
      link: '/level0'
    },
    {
      label: 'Level 1',
      link: '/level1'
    },
    {
      label: 'Level 2',
      link: '/level2'
    },
    {
      label: 'Level 3',
      link: '/level3'
    },
    {
      label: 'Level 4',
      link: '/level4'
    },
  ];

  return (
    <div className="bg-secondary-lightest">
      <Breadcrumbs
        list={list}
        onClick={link => console.log(`on-click: ${link}`)}
      />
    </div>
  );
}
```# Button

Buttons initiate actions and indicate what will happen after interacting with them.

### Code Examples

#### Components Button Button All

```jsx
import { Button } from '@innovaccer/design-system';

() => {
  const type = 'button';
  const children = 'Open';

  return (
    <Button type={type} onClick={action('button-clicked')} aria-label="Open">
      {children}
    </Button>
  );
}
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => {
  const appearances = ['basic', 'primary', 'alert', 'transparent'];

  return (
    <div className="d-flex w-75 justify-content-between">
      {appearances.map((appear, ind) => {
        return (
          <Button key={ind} onClick={action('button-clicked')} appearance={appear} aria-label={`${appear}`}>
            {appear.charAt(0).toUpperCase() + appear.slice(1)}
          </Button>
        );
      })}
    </div>
  );
}
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <Button appearance="alert" aria-label="Delete">
    Delete
  </Button>
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <Button appearance="basic" size="regular" aria-label="Cancel">
    Cancel
  </Button>
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <Button appearance="primary" size="regular" aria-label="Submit your response">
    Submit your response
  </Button>
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <Button appearance="transparent" aria-label="Re-evaluate">
    Re-evaluate
  </Button>
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <Button appearance="primary" size="regular" expanded={true} aria-label="Login">
    Login
  </Button>
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <Button appearance="basic" icon="keyboard_arrow_right" aria-label="Next in rank" tooltip="Next in rank" />
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <div className="d-inline-flex">
    <Button className="mr-2" size="tiny" icon="content_copy" aria-label="Copy" tooltip="Copy" />
    <Button className="mr-2" size="tiny" icon="content_paste" aria-label="Paste" tooltip="Paste" />
    <Button size="tiny" icon="delete" aria-label="Delete" tooltip="Delete" />
  </div>
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <Button icon="get_app" iconAlign="left" aria-label="Download">
    Download
  </Button>
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <Button icon="arrow_forward" iconAlign="right" aria-label="Next in rank">
    Next in rank
  </Button>
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => (
  <div className="d-flex">
    <Button size="tiny" className="mr-2" aria-label="Copy">
      Copy
    </Button>
    <Button size="tiny" className="mr-2" aria-label="Paste">
      Paste
    </Button>
    <Button size="tiny" aria-label="Delete">
      Delete
    </Button>
  </div>
)
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => <Button loading={true} aria-label="loading" />
```


#### Button

```jsx
import { Button } from '@innovaccer/design-system';

() => {
  const sizes = ['tiny', 'regular', 'large'];

  return (
    <div className="d-flex justify-content-between w-50">
      {sizes.map((ButtonSize, ind) => {
        return (
          <Button
            key={ind}
            size={ButtonSize}
            appearance={'primary'}
            aria-label={`${ButtonSize}`}
            onClick={action('button-clicked')}
          >
            {ButtonSize.charAt(0).toUpperCase() + ButtonSize.slice(1)}
          </Button>
        );
      })}
    </div>
  );
}
```


#### Button

```jsx
import { Button, Menu } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <Button className="mr-2" aria-label="Request review">
        Request review
      </Button>
      <div className="mb-10">
        <Menu trigger={<Menu.Trigger />}>
          <Menu.List>
            <Menu.Item>Download All</Menu.Item>
            <Menu.Item>Download Selected</Menu.Item>
          </Menu.List>
        </Menu>
      </div>
    </div>
  );
}
```


#### Button

```jsx
import { Button, Text } from '@innovaccer/design-system';

() => {
  const children = 'Delete';

  return (
    <div className="d-flex w-50 justify-content-between">
      <div>
        <Button onClick={action('button-clicked')} appearance={'alert'} aria-label="Delete">
          {children}
        </Button>
        <br />
        <Text weight="strong">Default</Text>
      </div>
      <div>
        <Button onClick={action('button-clicked')} appearance={'alert'} disabled={true} aria-label="Delete">
          {children}
        </Button>
        <br />
        <Text weight="strong">Disabled</Text>
      </div>
      <div>
        <Button onClick={action('button-clicked')} appearance={'alert'} loading={true} aria-label="Loading">
          {''}
        </Button>
        <br />
        <Text weight="strong">Loading</Text>
      </div>
    </div>
  );
}
```


#### Button

```jsx
import { Button, Text } from '@innovaccer/design-system';

() => {
  const children = 'Open';

  return (
    <div className="d-flex w-75 justify-content-between">
      <div>
        <Button onClick={action('button-clicked')} appearance={'basic'} aria-label="Open">
          {children}
        </Button>
        <br />
        <Text weight="strong">Default</Text>
      </div>
      <div>
        <Button onClick={action('button-clicked')} appearance={'basic'} disabled={true} aria-label="Open">
          {children}
        </Button>
        <br />
        <Text weight="strong">Disabled</Text>
      </div>
      <div>
        <Button onClick={action('button-clicked')} appearance={'basic'} loading={true} aria-label="Loading">
          {''}
        </Button>
        <br />
        <Text weight="strong">Loading</Text>
      </div>
      <div>
        <Button
          onClick={action('button-clicked')}
          appearance={'basic'}
          size={'regular'}
          selected={true}
          aria-label="Selected"
        >
          {children}
        </Button>
        <br />
        <Text weight="strong">Selected</Text>
      </div>
      <div>
        <Button
          onClick={action('button-clicked')}
          appearance={'basic'}
          selected={true}
          icon="events"
          aria-label="Selected"
        />
        <br />
        <Text weight="strong">Selected Icon</Text>
      </div>
    </div>
  );
}
```


#### Button

```jsx
import { Button, Text } from '@innovaccer/design-system';

() => {
  const children = 'Login';

  return (
    <div className="d-flex w-50 justify-content-between">
      <div>
        <Button onClick={action('button-clicked')} appearance={'primary'} aria-label="Login">
          {children}
        </Button>
        <br />
        <Text weight="strong">Default</Text>
      </div>
      <div>
        <Button onClick={action('button-clicked')} appearance={'primary'} disabled={true} aria-label="Login">
          {children}
        </Button>
        <br />
        <Text weight="strong">Disabled</Text>
      </div>
      <div>
        <Button onClick={action('button-clicked')} appearance={'primary'} loading={true} aria-label="Loading">
          {''}
        </Button>
        <br />
        <Text weight="strong">Loading</Text>
      </div>
    </div>
  );
}
```


#### Button

```jsx
import { Button, Text } from '@innovaccer/design-system';

() => {
  const children = 'Open';

  return (
    <div className="d-flex w-75 justify-content-between">
      <div>
        <Button onClick={action('button-clicked')} appearance={'transparent'} aria-label="Open">
          {children}
        </Button>
        <br />
        <Text weight="strong">Default</Text>
      </div>
      <div>
        <Button onClick={action('button-clicked')} appearance={'transparent'} disabled={true} aria-label="Open">
          {children}
        </Button>
        <br />
        <Text weight="strong">Disabled</Text>
      </div>
      <div>
        <Button onClick={action('button-clicked')} appearance={'transparent'} loading={true} aria-label="loading">
          {''}
        </Button>
        <br />
        <Text weight="strong">Loading</Text>
      </div>
      <div>
        <Button onClick={action('button-clicked')} appearance={'transparent'} selected={true} aria-label="Open">
          {children}
        </Button>
        <br />
        <Text weight="strong">Selected</Text>
      </div>
      <div>
        <Button
          onClick={action('button-clicked')}
          appearance={'transparent'}
          selected={true}
          icon="events"
          aria-label="Events"
        />
        <br />
        <Text weight="strong">Selected Icon</Text>
      </div>
    </div>
  );
}
```# Calendar

Calendar lets users select a date.

### Code Examples

#### Components Calendar All

```jsx
import { Calendar } from '@innovaccer/design-system';

() => {
  const monthsInView = 1;

  const dateValue = new Date('Jan 11 2023');

  const view = 'date';

  const rangePicker = false;

  const rangeLimit = 0;

  const firstDayOfWeek = 'saturday';

  const disabledBefore = new Date('Jan 20 2015');

  const disabledAfter = new Date('Jan 20 2028');

  const jumpView = true;

  const yearNav = -1;

  const monthNav = -1;

  const attr = {};
  if (disabledBefore) attr.disabledBefore = disabledBefore;
  if (disabledAfter) attr.disabledAfter = disabledAfter;
  if (rangeLimit) attr.rangeLimit = rangeLimit;
  if (yearNav !== -1) attr.yearNav = yearNav;
  if (monthNav !== -1) attr.monthNav = monthNav;

  // we redefine this function here because in storybook.json we do not get imported functions.

  const isValid = (validators, ...value) => {
    const iterator = Array.isArray(validators) ? validators : [validators];

    return iterator.every((validator) => validator(...value));
  };

  const translateToDate = (format, val, validators) => {
    if (isValid(validators, val, format)) {
      const separator = format.includes('/') ? '/' : '-';

      let year = -1,
        month = -1,
        date = -1;
      const v = val.split(separator);
      format.split(separator).forEach((f, i) => {
        switch (f) {
          case 'mm':
            month = +v[i] - 1;
            break;
          case 'yyyy':
            year = +v[i];
            break;
          case 'dd':
            date = +v[i];
            break;
        }
      });
      const d = convertToDate({ year, month, date });
      return d;
    } else {
      return undefined;
    }
  };

  const convertToDate = (d, format, validators) => {
    let dateVal;

    if (d) {
      if (typeof d === 'number') {
        dateVal = new Date(d);
      } else if (typeof d === 'string') {
        return format ? translateToDate(format, d, validators) : undefined;
      } else if (!(d instanceof Date)) {
        const { year, month, date } = d;
        dateVal = new Date(year, month, date, 0, 0, 0);
      } else {
        dateVal = d;
      }
    }
    return dateVal;
  };

  return (
    <Calendar
      monthsInView={monthsInView}
      rangePicker={rangePicker}
      jumpView={jumpView}
      date={convertToDate(dateValue)}
      events={{
        '01/12/2023': true,
      }}
      onDateChange={(currDate) => action(`on date change : ${currDate}`)()}
      onRangeChange={(sDate, eDate) => action(`on range change: ${sDate} - ${eDate}`)()}
      view={view}
      firstDayOfWeek={firstDayOfWeek}
      {...attr}
    />
  );
}
```


#### Calendar

```jsx
import { Heading, Calendar } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex mt-8">
      <div className="mr-8">
        <Heading>size: small</Heading>
        <Calendar events={{ '12/21/2023': true }} date={new Date('12/21/2023')} size={'small'} />
      </div>

      <div>
        <Heading>size: large</Heading>
        <Calendar events={{ '12/20/2023': true }} date={new Date('12/21/2023')} size={'large'} />
      </div>
    </div>
  );
}
```


#### Calendar

```jsx
import { Heading, Calendar } from '@innovaccer/design-system';

() => {
  const view = ['date', 'month', 'year'];

  return (
    <>
      <Heading>Disabled before</Heading>
      <div className="d-flex mb-8 justify-content-between">
        {view.map((v, index) => (
          <Calendar key={index} date={new Date(2023, 2, 15)} disabledBefore={new Date(2023, 2, 10)} view={v} />
        ))}
      </div>

      <Heading>Disabled after</Heading>
      <div className="d-flex mb-8 justify-content-between">
        {view.map((v, index) => (
          <Calendar key={index} date={new Date(2023, 2, 15)} disabledAfter={new Date(2023, 2, 20)} view={v} />
        ))}
      </div>

      <Heading>Disabled before and Disabled after</Heading>
      <div className="d-flex justify-content-between">
        {view.map((v, index) => (
          <Calendar
            key={index}
            date={new Date(2023, 2, 15)}
            disabledBefore={new Date(2023, 2, 10)}
            disabledAfter={new Date(2023, 2, 20)}
            view={v}
          />
        ))}
      </div>
    </>
  );
}
```


#### Calendar

```jsx
import { Calendar } from '@innovaccer/design-system';

() => {
  const values = ['sunday', 'monday', 'tuesday', 'wednesday', 'thursday', 'friday', 'saturday'];

  return (
    <div className="d-flex flex-wrap">
      {values.map((v, index) => (
        <Calendar className="mr-9 mt-5" key={index} date={new Date(2023, 2, 1)} firstDayOfWeek={v} />
      ))}
    </div>
  );
}
```


#### Calendar

```jsx
import { Heading, Calendar } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex mt-8">
      <div className="mr-8">
        <Heading>size: small</Heading>
        <Calendar date={new Date(2023, 2, 15)} size={'small'} view="date" />
      </div>

      <div>
        <Heading>size: large</Heading>
        <Calendar date={new Date(2023, 2, 15)} size={'large'} view="date" />
      </div>
    </div>
  );
}
```


#### Calendar

```jsx
import { Heading, Calendar } from '@innovaccer/design-system';

() => {
  const view = ['year', 'month', 'date'];

  return (
    <>
      <div className="mt-8">
        <Heading>size: small</Heading>
        <div className="d-flex justify-content-between">
          {view.map((v, index) => (
            <Calendar key={index} date={new Date(2023, 2, 15)} size={'small'} view={v} />
          ))}
        </div>
      </div>

      <div className="mt-8">
        <Heading>size: large</Heading>
        <div className="d-flex">
          {view.map((v, index) => (
            <Calendar key={index} date={new Date(2023, 2, 15)} size={'large'} view={v} />
          ))}
        </div>
      </div>
    </>
  );
}
```# Caption



### Code Examples

#### Caption

```jsx
import {  } from '@innovaccer/design-system';

() => <></>
```# Card

Cards act as containers to group related information together.

### Code Examples

#### Components Card All

```jsx
import { Card, CardHeader, Text, CardBody, CardFooter, Button, CardSubdued } from '@innovaccer/design-system';

/*
// style.css
.Card-wrapper {
    height: 250px;
}
*/

() => {
  const shadow = 'default';

  return (
    <>
      <Card shadow={shadow} className="w-50 Card-wrapper">
        <CardHeader>
          <Text weight="strong" size="large">
            Card Heading
          </Text>
        </CardHeader>
        <CardBody>
          <div>Card Body</div>
        </CardBody>
        <CardFooter className="justify-content-end" withSeperator={false}>
          <>
            <Button appearance="basic">Cancel</Button>
            <Button appearance="primary" className="ml-4">
              Submit
            </Button>
          </>
        </CardFooter>
      </Card>
      <Card className="mt-5 w-50">
        <CardHeader>
          <Text weight="strong" size="large">
            Card Heading
          </Text>
        </CardHeader>
        <CardBody>
          <div>Card Body</div>
        </CardBody>
        <CardSubdued className='mt-5'>Subdued section.</CardSubdued>
      </Card>
    </>
  );
}
```


#### Components Card Card Within A Card

```jsx
import { Row, Column, Card, CardHeader, Heading, CardBody, Text, Badge, CardFooter } from '@innovaccer/design-system';


  () => {
  return (
    <Row>
      <Column size="8">
        <Card>
          <CardHeader>
            <Heading size="s">Managed Plans</Heading>
          </CardHeader>
          <CardBody>
            <Card shadow="none" className="mb-6">
              <CardHeader className="d-flex justify-content-between">
                <Text weight="strong">PRIMARY</Text>
                <Badge appearance="accent4">ACTIVE</Badge>
              </CardHeader>
              <CardBody>
                <Text appearance="disabled">MSSP - Track 3</Text>
                <br />
                <Text small={true}>Medicare</Text>
                <br />
                <div className="py-6">
                  <Text small={true} appearance="disabled">
                    Subscriber
                  </Text>
                  <br />
                  <Text appearance="disabled">LAWSON, JOY (Self)</Text>
                  <br />
                  <Text weight="medium">ZGP123456789</Text>
                </div>
              </CardBody>

              <CardFooter className="position-relative" withSeperator={false}>
                <div>
                  <Text appearance="disabled" small={true}>
                    Last attr:
                  </Text>
                  <Text small={true} className="ml-3">
                    04/19
                  </Text>
                  <Text appearance="disabled" small={true} className="ml-7">
                    Payer ID:
                  </Text>
                  <Text small={true} className="ml-3">
                    001
                  </Text>
                </div>
              </CardFooter>
            </Card>

            <Card shadow="none" className="mb-6">
              <CardHeader className="d-flex justify-content-between">
                <Text weight="strong" appearance="disabled">
                  SECONDARY
                </Text>
                <Badge>INACTIVE</Badge>
              </CardHeader>
              <CardBody>
                <Text appearance="disabled">Community Plan</Text>
                <br />
                <Text small={true}>Blue Shield of California</Text>
                <br />
                <div className="py-6">
                  <Text small={true} appearance="disabled">
                    Subscriber
                  </Text>
                  <br />
                  <Text appearance="disabled">LAWSON, MICHAEL (Spouse)</Text>
                  <br />
                  <Text weight="medium">HKA987654321</Text>
                </div>
              </CardBody>
              <CardFooter className="position-relative" withSeperator={false}>
                <div>
                  <Text appearance="disabled" small={true}>
                    Last attr:
                  </Text>
                  <Text small={true} className="ml-3">
                    11/18
                  </Text>
                  <Text appearance="disabled" small={true} className="ml-7">
                    Payer ID:
                  </Text>
                  <Text small={true} className="ml-3">
                    042
                  </Text>
                </div>
              </CardFooter>
            </Card>
          </CardBody>
        </Card>
      </Column>
    </Row>
  )
}

```


#### Components Card Empty Card

```jsx
import { Row, Column, Card, CardHeader, Heading, CardBody, EmptyState, Button } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column size="8">
        <Card>
          <CardHeader>
            <Heading size="s">Daily progress</Heading>
          </CardHeader>
          <CardBody>
            <EmptyState
              title="Unable to fetch data"
              description="Sorry there was a technical issue while getting this data. Please try again."
              imageSrc={image}
              size="small"
              className="pb-6"
            >
              <Button icon="refresh" iconAlign="left" className="mt-3">
                Reload
              </Button>
            </EmptyState>
          </CardBody>
        </Card>
      </Column>
    </Row>
  );
}
```


#### Card

```jsx
import { Row, Column, Card, CardHeader, Heading, CardBody, Paragraph, Radio, Text, CardSubdued, StatusHint } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column size="7">
        <Card>
          <CardHeader>
            <Heading size="s">Set timing</Heading>
          </CardHeader>
          <CardBody>
            <Paragraph>
              After the campaign starts, the outreach attempt will be made with the recipients according to the sender's
              preferred timings.
            </Paragraph>
            <Row>
              <Column size="12" className="pt-4">
                <Radio label="Send now" name="gender" value="Checkbox" defaultChecked={true} />
                <Text small={true} appearance="disabled" className="ml-7">
                  Campaign will start immediately
                </Text>
              </Column>
              <Column size="12" className="py-4">
                <Radio label="Schedule for later" name="gender" value="Checkbox" />
                <Text small={true} appearance="disabled" className="ml-7">
                  Campaign will not start immediately
                </Text>
              </Column>
            </Row>
          </CardBody>

          <CardSubdued>
            <Text weight="strong" small={true}>
              SELECTED RECIPIENTS
            </Text>
            <div className="pt-5">
              <StatusHint appearance="success">437 wil receive the message.</StatusHint>
              <StatusHint appearance="alert">42 have opted out or never agreed to receive messages.</StatusHint>
            </div>
          </CardSubdued>
        </Card>
      </Column>
    </Row>
  );
}
```


#### Components Card Scrollable Content

```jsx
import { Paragraph, Text, Card, CardHeader, Heading, List } from '@innovaccer/design-system';



() => {

  const data = [
  {
    "data": {
      "title": "Reminder for due lab tests",
      "subTitle": "ENG. +1 Hi [recipient.name]! Your (test) is overdue. Please get in touch with [recipient.PCPI..."
    }
  },
  {
    "data": {
      "title": "Reminder for due lab tests",
      "subTitle": "ENG. +1 Hi [recipient.name]! Your (test) is overdue. Please get in touch with [recipient.PCPI..."
    }
  },
  {
    "data": {
      "title": "Reminder for upcoming lab test",
      "subTitle": "ENG. «1 Hi [recipient.name]! Your [test] is scheduled for [test.date]. Please get in..."
    }
  },
  {
    "data": {
      "title": "Reminder for due lab tests",
      "subTitle": "ENG -1 Hi [recipient.name] Your [test] is overdue. Please get in touch with [recipiert.PCP}..."
    }
  },
  {
    "data": {
      "title": "Reminder for due lab tests",
      "subTitle": "ENG. +1 Hi [recipient.name] Your (test] is overdue. Please get in touch with (recipient. PCP}..."
    }
  },
  {
    "data": {
      "title": "Reminder for due lab tests",
      "subTitle": "ENG. +1 Hi [recipient.name]! Your (test) is overdue. Please get in touch with [recipient.PCPI..."
    }
  },
  {
    "data": {
      "title": "Reminder for due lab tests",
      "subTitle": "ENG. +1 Hi [recipient.name]! Your (test) is overdue. Please get in touch with [recipient.PCPI..."
    }
  },
  {
    "data": {
      "title": "Reminder for upcoming lab test",
      "subTitle": "ENG. «1 Hi [recipient.name]! Your [test] is scheduled for [test.date]. Please get in..."
    }
  },
  {
    "data": {
      "title": "Reminder for due lab tests",
      "subTitle": "ENG -1 Hi [recipient.name] Your [test] is overdue. Please get in touch with [recipiert.PCP}..."
    }
  },
  {
    "data": {
      "title": "Reminder for due lab tests",
      "subTitle": "ENG. +1 Hi [recipient.name] Your (test] is overdue. Please get in touch with (recipient. PCP}..."
    }
  }
];

  const schema = [
    {
      width: '100%',
      name: 'data',
      displayName: '',
      cellRenderer: (props) => {
        return (
          <>
          <Paragraph>
            <Text weight="strong">
              {props.data.data.title}
            </Text>
            <br />
            <Text>
              {props.data.data.subTitle}
            </Text>

          </Paragraph>
          </>
        );
      }
    }
  ];

  return (
    <div>
      <Card className="">
        <CardHeader>
          <Heading size="s">Use a template</Heading>
        </CardHeader>
        <div className="vh-50">
          <List
            data={data}
            schema={schema}
            withHeader={true}
            headerOptions={{
              withSearch: true,
              dynamicColumn: false
            }}
            withPagination={true}
            pageSize={5}
          />
        </div>
      </Card>
    </div>
  );
};

```


#### Components Card Shadow

```jsx
import { Card } from '@innovaccer/design-system';

() => {
  const shadows = ['none', 'shadow10', 'shadow20', 'shadow30'];
  return (
    <div className="d-flex justify-content-between w-75">
      {shadows.map((shadow) => {
        return (
          <Card shadow={shadow} key={shadow}>
            <div className="p-8">{shadow}</div>
          </Card>
        );
      })}
    </div>
  );
}
```


#### Components Card Type Default Card

```jsx
import { Card } from '@innovaccer/design-system';

() => {
  return (
    <Card>
      <div className="p-8" />
    </Card>
  );
}
```


#### Components Card Type Flat

```jsx
import { Card } from '@innovaccer/design-system';

() => {
  return (
    <Card shadow="none">
      <div className="p-8" />
    </Card>
  );
}
```


#### CardSubdued

```jsx
import { CardSubdued } from '@innovaccer/design-system';

() => {
  return (
    <CardSubdued>
      <div className="p-8" />
    </CardSubdued>
  );
}
```# ChatMessage



### Code Examples

#### Components Chat Chat Message

```jsx
import { ChatMessage } from '@innovaccer/design-system';

() => {
  const type = 'incoming';
  const statusType = 'sent';
  const isTyping = false;
  const message = 'Hello, there.';
  const typingText = 'Typing..';
  const failedMessage = 'Click to retry';
  const sendingMessage = 'Sending';

  const options = {
    type,
    isTyping,
    typingText,
    failedMessage,
    sendingMessage,
    text: message,
    statusOptions: { type: statusType, time: '10:11 AM' },
  };

  return (
    <div className="w-25">
      <ChatMessage {...options} />
    </div>
  );
}
```# Checkbox

Checkbox lets users select one or more values.

### Code Examples

#### Components Checkbox All

```jsx
import { Checkbox } from '@innovaccer/design-system';

() => {
  const size = 'regular';

  const label = 'Checkbox';

  const [checked, setChecked] = React.useState(false);

  const [indeterminate, setIndeterminate] = React.useState(false);

  const disabled = false;

  const onChangeHandler = (event) => {
    setChecked(!checked);
    setIndeterminate(!indeterminate);
    return action(`onChange: ${event.target.checked}`)();
  };

  return (
    <Checkbox
      checked={checked}
      indeterminate={indeterminate}
      disabled={disabled}
      size={size}
      label={label}
      onChange={onChangeHandler}
    />
  );
}
```


#### Checkbox

```jsx
import { ChoiceList } from '@innovaccer/design-system';

() => {
  const labelHorizontal = 'Horizontal Alignment';
  const alignmentHorizontal = 'horizontal';
  const days = [
    { label: 'Mon', name: 'days', value: 'mon' },
    { label: 'Tue', name: 'days', value: 'tue' },
    { label: 'Wed', name: 'days', value: 'wed' },
    { label: 'Thu', name: 'days', value: 'thu' },
    { label: 'Fri', name: 'days', value: 'fri' },
    { label: 'Sat', name: 'days', value: 'sat' },
    { label: 'Sun', name: 'days', value: 'sun' },
  ];

  return (
    <ChoiceList
      choices={days}
      selected={['mon', 'tue']}
      allowMultiple={true}
      title={labelHorizontal}
      alignment={alignmentHorizontal}
      onChange={() => {}}
    />
  );
}
```


#### Components Checkbox Checkbox Group Nested

```jsx
import { Checkbox } from '@innovaccer/design-system';

() => {
  const labels = ['Diabetes Eye Exam', 'HbA1c Test in last 12 months', 'Falls Risk Assessment'];

  const childArray = [true, true, false];

  const [checked, setChecked] = React.useState(childArray);
  const [parentStatus, setParentStatus] = React.useState({ checked: false, indeterminate: true });

  const handleParentChange = (event) => {
    const updatedArray = [...childArray].fill(event.target.checked);
    setChecked(updatedArray);
    setParentStatus({ checked: event.target.checked, indeterminate: event.target.indeterminate });
  };

  const handleChildChange = (event, index) => {
    const updateCheck = [...checked];
    updateCheck[index] = event.target.checked;
    const totalCount = labels.length;
    const countT = updateCheck.filter(Boolean).length;
    const status = countT < totalCount;
    const obj = (countT > 0) ? { checked: !status, indeterminate: status } : { checked: !status, indeterminate: false };
    setChecked(updateCheck);
    setParentStatus(obj);
  };

  return (
    <div>
      <Checkbox
        checked={parentStatus.checked}
        indeterminate={parentStatus.indeterminate}
        label={'Measures'}
        onChange={handleParentChange}
        value={'Measures'}
      />
      <div className="d-flex flex-column pl-7">
        {
          labels.map((label, ind) => {
            return (
              <Checkbox
                key={`checkbox-${ind}`}
                label={label}
                checked={checked[ind]}
                value={label}
                onChange={c => handleChildChange(c, ind)}
                className='mt-3'
              />
            );
          })
        }
      </div>
    </div>
  );
}
```


#### Checkbox

```jsx
import { ChoiceList } from '@innovaccer/design-system';

() => {
  const labelVertical = 'Vertical Alignment';
  const alignmentVertical = 'vertical';
  const days = [
    { label: 'Mon', name: 'days', value: 'mon' },
    { label: 'Tue', name: 'days', value: 'tue' },
    { label: 'Wed', name: 'days', value: 'wed' },
    { label: 'Thu', name: 'days', value: 'thu' },
    { label: 'Fri', name: 'days', value: 'fri' },
    { label: 'Sat', name: 'days', value: 'sat' },
    { label: 'Sun', name: 'days', value: 'sun' },
  ];

  return (
    <ChoiceList
      choices={days}
      selected={['mon', 'tue']}
      allowMultiple={true}
      title={labelVertical}
      alignment={alignmentVertical}
      onChange={() => {}}
    />
  );
}
```


#### Checkbox

```jsx
import { Checkbox } from '@innovaccer/design-system';

() => <Checkbox label="Emergency contact" defaultChecked={true} />
```


#### Checkbox

```jsx
import { Checkbox } from '@innovaccer/design-system';

() => (
  <Checkbox className="w-25" label="Patient with impaired physical mobility and care deficits." />
)
```


#### Components Checkbox Variants Controlled Checkbox

```jsx
import { Checkbox } from '@innovaccer/design-system';

() => {
  const [checked, setChecked] = React.useState(false);

  const handleParentChange = (event) => {
    const updatedChecked = event.target.checked;
    setChecked(updatedChecked);
  };

  return (
      <Checkbox
        checked={checked}
        label={'Innovaccer'}
        onChange={handleParentChange}
        value={'Innovaccer'}
      />
  );
}
```


#### Checkbox

```jsx
import { Label, Checkbox } from '@innovaccer/design-system';

() => {
  const label = 'Checkbox';
  return (
    <div className="d-flex">
      <div className="mr-7">
        <Label withInput={true}>Checked</Label>
        <Checkbox checked={true} disabled={true} label={label} />
      </div>
      <div className="mr-7">
        <Label withInput={true}>Unchecked</Label>
        <Checkbox checked={false} disabled={true} label={label} />
      </div>
      <div>
        <Label withInput={true}>Indeterminate</Label>
        <Checkbox indeterminate={true} disabled={true} label={label} />
      </div>
    </div>
  );
}
```


#### Checkbox

```jsx
import { Checkbox } from '@innovaccer/design-system';

() => {
  const size = 'regular';

  const label = 'Checkbox';

  const [checked, setChecked] = React.useState(false);

  const [indeterminate, setIndeterminate] = React.useState(false);

  const disabled = false;

  const onChangeHandler = (event) => {
    setChecked(!checked);
    setIndeterminate(!indeterminate);
    return action(`onChange: ${event.target.checked}`)();
  };

  return (
    <Checkbox
      error={true}
      checked={checked}
      indeterminate={indeterminate}
      disabled={disabled}
      size={size}
      label={label}
      onChange={onChangeHandler}
    />
  );
}
```


#### Checkbox

```jsx
import { Label, Checkbox } from '@innovaccer/design-system';

() => {
  const sizes = ['tiny', 'regular'];
  const label = 'Checkbox';
  return (
    <div className="d-flex">
      {sizes.map((CheckboxSize, ind) => {
        return (
          <div key={ind} className="mr-7">
            <Label withInput={true}>{CheckboxSize.charAt(0).toUpperCase() + CheckboxSize.slice(1)}</Label>
            <Checkbox disabled={false} size={CheckboxSize} label={label} />
          </div>
        );
      })}
    </div>
  );
}
```


#### Components Checkbox With Help Text

```jsx
import { Checkbox } from '@innovaccer/design-system';

() => {
  return (
    <Checkbox
      label={'Guardian'}
      helpText={'A member legally responsible for the care of the patient.'}
      className="w-50"
    />
  );
}
```# Chip



### Code Examples

#### Components Chip Chip All

```jsx
import { Chip } from '@innovaccer/design-system';

() => {
  const type = 'selection';

  const label = 'Chip Label';

  const icon = 'assessment';

  const disabled = false;

  let clearButton;
  if (type !== 'action') {
    clearButton = true;
  }

  let selected;
  if (type === 'selection') {
    selected = false;
  }
  return (
    <Chip
      icon={icon}
      label={label}
      clearButton={clearButton}
      disabled={disabled}
      type={type}
      onClose={action(`onClose: ${label}`)}
      onClick={action(`onClick: ${label}`)}
      selected={selected}
      name={'chip'}
    />
  );
}
```


#### Components Chip Chip Custom Label

```jsx
import { Chip } from '@innovaccer/design-system';

() => {
  const customLabelData1 = [
    ['Age=', '60yrs', { selected: true }],
    ['Age:', '18yrs to 60yrs', { selected: false }],
    ['Age>=', '18yrs', { selected: false, disabled: true }],
  ];

  const customLabelData2 = [
    ['Provider City:', 'San Diego', { selected: true }],
    ['Provider City:', 'San Diego, Chicago', { selected: false }],
    ['Provider City:', '3 selected', { selected: false, disabled: true }],
  ];

  const customLabelData3 = [
    ['Creation Date>=', '01/01/2020', { selected: true }],
    ['Creation Date=', '01/01/2020', { icon: 'assessment', selected: false }],
    ['Creation Date:', 'last 6 months', { icon: 'assessment', selected: false, disabled: true }],
  ];

  const renderChips = (
    <>
      <div className="d-flex justify-content-around flex-wrap">
        {customLabelData1.map((customLabel, index) => (
          <Chip
            className="mb-6"
            key={index}
            label={customLabel[1]}
            labelPrefix={customLabel[0]}
            clearButton={true}
            name={customLabel[0]}
            type="selection"
            selected={customLabel[2].selected}
            disabled={customLabel[2].disabled}
          />
        ))}
      </div>
      <div className="d-flex justify-content-around flex-wrap">
        {customLabelData2.map((customLabel, index) => (
          <Chip
            icon={customLabel[2].icon}
            className="mb-6"
            key={index}
            label={customLabel[1]}
            labelPrefix={customLabel[0]}
            clearButton={true}
            name={customLabel[0]}
            type="selection"
            selected={customLabel[2].selected}
            disabled={customLabel[2].disabled}
          />
        ))}
      </div>
      <div className="d-flex justify-content-around flex-wrap">
        {customLabelData3.map((customLabel, index) => (
          <Chip
            className="mb-6"
            key={index}
            label={customLabel[1]}
            labelPrefix={customLabel[0]}
            icon={customLabel[2].icon}
            clearButton={true}
            name={customLabel[0]}
            type="selection"
            selected={customLabel[2].selected}
            disabled={customLabel[2].disabled}
          />
        ))}
      </div>
    </>
  );

  return <div>{renderChips}</div>;
}
```


#### Components Chip Chip Overflow Behavior

```jsx
import { Row, Column, Chip } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column>
        <Chip
          label="Dan Mckenzie Farland Bartholomew"
          clearButton={true}
          name="Dan Mckenzie Farland Bartholomew"
          type="input"
        />
      </Column>
      <Column>
        <Chip
          labelPrefix="Provider city :"
          label="Los Angeles, California"
          clearButton={true}
          name="Provider city :"
          type="input"
        />
      </Column>
      <Column>
        <Chip
          label="LA"
          labelPrefix="Provider city is very very very long :"
          name="Provider city is very very very long :"
          clearButton={true}
          type="input"
        />
      </Column>
    </Row>
  );
}
```


#### Chip

```jsx
import { Chip, Text } from '@innovaccer/design-system';

() => {
  const icon = 'assessment';
  const label = 'Action';
  return (
    <div className="d-flex justify-content-between w-50">
      {BooleanValue.map((booleanvalue, ind) => {
        return (
          <div key={ind}>
            <Chip icon={icon} label={label} disabled={booleanvalue} type="action" name={'chip'} />
            <br />
            <br />
            <Text weight="strong">{`Disabled: ${booleanvalue}`}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### Chip

```jsx
import { Chip, Text } from '@innovaccer/design-system';

() => {
  const icon = 'assessment';
  const label = 'Input';
  return (
    <div className="d-flex justify-content-between w-50">
      {BooleanValue.map((booleanvalue, ind) => {
        return (
          <div key={ind}>
            <Chip icon={icon} label={label} clearButton={true} disabled={booleanvalue} type="input" name={'chip'} />
            <br />
            <br />
            <Text weight="strong">{`Disabled: ${booleanvalue}`}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### Chip

```jsx
import { Chip, Text } from '@innovaccer/design-system';

() => {
  const icon = 'assessment';
  const label = 'Selection';

  return (
    <div className="d-flex justify-content-between">
      {BooleanValue.map((booleanvalue, ind) => {
        return (
          <div key={ind}>
            <Chip
              icon={icon}
              label={label}
              clearButton={true}
              disabled={booleanvalue}
              type="selection"
              selected={false}
              name={'chip'}
            />
            <br />
            <br />
            <Text weight="strong">{`Disabled: ${booleanvalue}`}</Text>
          </div>
        );
      })}
      <div>
        <Chip
          icon={icon}
          label={label}
          clearButton={true}
          type="selection"
          onClose={action(`onClose: ${label}`)}
          onClick={action(`onClick: ${label}`)}
          selected={true}
          name={'chip'}
        />
        <br />
        <br />
        <Text weight="strong">Selected: true</Text>
      </div>
      <div>
        <Chip
          icon={icon}
          label={label}
          clearButton={true}
          type="selection"
          onClose={action(`onClose: ${label}`)}
          onClick={action(`onClick: ${label}`)}
          selected={true}
          disabled={true}
          name={'chip'}
        />
        <br />
        <br />
        <Text weight="strong">Selected: true</Text>
        <br></br>
        <Text weight="strong">Disabled: true</Text>
      </div>
    </div>
  );
}
```# ChipGroup



### Code Examples

#### Components Chip ChipGroup Action Chips

```jsx
import { ChipGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      label: 'Letter.pdf',
      icon: 'assessment',
      type: 'action',
      name: '1',
    },
    {
      label: 'Mail.pdf',
      icon: 'assessment',
      clearButton: true,
      type: 'action',
      name: '2',
    },
    {
      label: 'Draft.pdf',
      icon: 'assessment',
      clearButton: true,
      type: 'action',
      selected: true,
      name: '3',
    },
  ];

  return <ChipGroup list={list} onClick={action(`onClick event`)} />;
}
```


#### Components Chip ChipGroup Input Chips

```jsx
import { ChipGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      label: 'John',
      clearButton: true,
      type: 'input',
      name: '1',
    },
    {
      label: 'Locke',
      clearButton: true,
      type: 'input',
      name: '2',
    },
    {
      label: 'Nina',
      clearButton: true,
      type: 'input',
      name: '3',
    },
  ];

  return <ChipGroup list={list} onClose={action(`onClose event`)} onClick={action(`onClick event`)} />;
}
```


#### Components Chip ChipGroup Selection Chips

```jsx
import { ChipGroup } from '@innovaccer/design-system';

() => {
  const list = [
    {
      label: 'Call note',
      icon: 'assessment',
      clearButton: true,
      type: 'selection',
      name: '1',
    },
    {
      label: 'Visit note',
      icon: 'assessment',
      clearButton: true,
      type: 'selection',
      name: '2',
    },
    {
      label: 'Generic note',
      icon: 'assessment',
      clearButton: true,
      type: 'selection',
      name: '3',
    },
  ];

  return <ChipGroup list={list} onClose={action(`onClose event`)} onClick={action(`onClick event`)} />;
}
```# ChipInput



### Code Examples

#### Components Input ChipInput All

```jsx
import { ChipInput } from '@innovaccer/design-system';

() => {
  const allowDuplicates = false;
  const placeholder = 'Add value';
  const disabled = false;

  return (
    <ChipInput
      allowDuplicates={allowDuplicates}
      placeholder={placeholder}
      disabled={disabled}
      chipOptions={{ clearButton: true }}
    />
  );
}
```


#### Components Input ChipInput Chips In Single Line

```jsx
import { Label, ChipInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(['Anyone', 'Person with disability']);

  return (
    <>
      <Label withInput={true}>Population Focus</Label>
      <ChipInput
        value={value}
        chipOptions={{ clearButton: true }}
        onChange={setValue}
      />
    </>
  );
}
```


#### Components Input ChipInput Overflow Behavior

```jsx
import { Row, Column, Label, ChipInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(
    ['Anyone', 'Person with disability', 'Retired person from the armed forces']
  );

  return (
    <Row>
      <Column size={4}>
        <Label withInput={true}>Population Focus</Label>
        <ChipInput
          value={value}
          chipOptions={{ clearButton: true }}
          onChange={setValue}
        />
      </Column>
    </Row>
  );
}
```


#### Components Input ChipInput Variants Controlled

```jsx
import { ChipInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(['1024', '80']);

  return (
    <ChipInput
      value={value}
      placeholder="Add value"
      chipOptions={{ clearButton: true }}
      onChange={setValue}
    />
  );
}
```


#### Components Input ChipInput Variants Disabled

```jsx
import { ChipInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(['1024', '80']);

  return (
    <ChipInput
      value={value}
      chipOptions={{ clearButton: true }}
      onChange={setValue}
      disabled={true}
    />
  );
}
```# ChoiceList



### Code Examples

#### Components ChoiceList All

```jsx
import { ChoiceList } from '@innovaccer/design-system';

() => {
  const label = 'Gender';
  const gender = [
    { label: 'Male', name: 'gender', value: 'Male' },
    { label: 'Female', name: 'gender', value: 'Female' },
    { label: 'Other', name: 'gender', value: 'Other' },
  ];

  return <ChoiceList choices={gender} title={label} onChange={() => {}} />;
}
```


#### Components ChoiceList Alignment

```jsx
import { ChoiceList } from '@innovaccer/design-system';

() => {
  const label = 'Gender';
  const alignmentHorizontal = 'horizontal';
  const gender = [
    { label: 'Male', name: 'gender', value: 'Male' },
    { label: 'Female', name: 'gender', value: 'Female' },
    { label: 'Other', name: 'gender', value: 'Other' },
  ];
  const alignmentVertical = 'vertical';
  const allGender = [
    { label: 'Male', name: 'allGender', value: 'Male' },
    { label: 'Female', name: 'allGender', value: 'Female' },
    { label: 'Other', name: 'allGender', value: 'Other' },
  ];

  return (
    <>
      <ChoiceList choices={gender} title={label} alignment={alignmentHorizontal} onChange={() => {}} />
      <div className="mt-8">
        <ChoiceList choices={allGender} title={label} alignment={alignmentVertical} onChange={() => {}} />
      </div>
    </>
  );
}
```


#### Components ChoiceList Allow Multiple

```jsx
import { ChoiceList } from '@innovaccer/design-system';

() => {
  const label = 'Days';
  const alignment = 'horizontal';
  const days = [
    { label: 'Mon', name: 'days', value: 'mon' },
    { label: 'Tue', name: 'days', value: 'tue' },
    { label: 'Wed', name: 'days', value: 'wed' },
    { label: 'Thu', name: 'days', value: 'thu' },
    { label: 'Fri', name: 'days', value: 'fri' },
    { label: 'Sat', name: 'days', value: 'sat' },
    { label: 'Sun', name: 'days', value: 'sun' },
  ];

  return <ChoiceList choices={days} title={label} alignment={alignment} allowMultiple={true} onChange={() => {}} />;
}
```


#### Components ChoiceList Controlled

```jsx
import { ChoiceList } from '@innovaccer/design-system';

() => {
  const label = 'Gender';
  const alignmentHorizontal = 'horizontal';
  const days = [
    { label: 'Mon', name: 'days', value: 'mon' },
    { label: 'Tue', name: 'days', value: 'tue' },
    { label: 'Wed', name: 'days', value: 'wed' },
    { label: 'Thu', name: 'days', value: 'thu' },
    { label: 'Fri', name: 'days', value: 'fri' },
    { label: 'Sat', name: 'days', value: 'sat' },
    { label: 'Sun', name: 'days', value: 'sun' },
  ];

  return (
    <>
      <ChoiceList
        selected={['mon', 'wed', 'sat']}
        choices={days}
        allowMultiple={true}
        title={label}
        alignment={alignmentHorizontal}
        onChange={() => {}}
      />
    </>
  );
}
```# Collapsible



### Code Examples

#### Components VerticalNav Collapsible All

```jsx
import { Collapsible, Icon, Text } from '@innovaccer/design-system';

() => {
  const [expanded, setExpanded] = React.useState(false);
  return (
      <Collapsible
        expanded={expanded}
        height="100vh"
        onToggle={setExpanded}
      >
        <div className="d-flex pt-4">
          <Icon name="events" className="d-flex align-items-center px-6 Text--regular" />
          {expanded && (
            <Text className="mr-6">Collapsible</Text>
          )}
        </div>
      </Collapsible>
  );
}
```


#### Components VerticalNav Collapsible Custom Trigger

```jsx
import { Icon, Heading, Collapsible, Text } from '@innovaccer/design-system';

() => {
  const [expanded, setExpanded] = React.useState(false);

  return (
    <div>
      <div className='d-flex align-items-center mb-3'>
        <Icon name="menu" className="cursor-pointer" onClick={() => setExpanded(!expanded) }></Icon>
        <Heading size='s' className="ml-4">Click to Open</Heading>
      </div>
      <Collapsible withTrigger={false} expanded={expanded} height="100vh">
        <div className="d-flex pt-4">
          <Icon name="events" className="d-flex align-items-center px-6 Text--regular" />
          {expanded && <Text className="mr-6">Collapsible</Text>}
        </div>
        </Collapsible>
    </div>
  );
}
```# Column



### Code Examples

#### Components Layout Column

```jsx
import { Row, Column } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column className="p-6 border bg-secondary-lightest">Column 1</Column>
      <Column className="p-6 border bg-secondary-lightest">Column 2</Column>
      <Column className="p-6 border bg-secondary-lightest">Column 3</Column>
      <Column className="p-6 border bg-secondary-lightest">Column 4</Column>
      <Column className="p-6 border bg-secondary-lightest">Column 5</Column>
    </Row>
  );
}
```


#### Components Layout Sizes

```jsx
import { Row, Column } from '@innovaccer/design-system';

() => {
  return (
    <>
      <Row>
        <Column className="p-6 border bg-secondary-lightest mr-4" size={10}>
          size=10
        </Column>
        <Column className="p-6 bg-secondary-lightest border">size=2</Column>
      </Row>
      <Row className="justify-space-between mt-6">
        <Column className="p-6 border bg-secondary-lightest mr-4" size={8}>
          size=8
        </Column>
        <Column className="p-6 bg-secondary-lightest border">size=4</Column>
      </Row>
      <Row className="justify-space-between mt-6">
        <Column className="p-6 border bg-secondary-lightest mr-4" size={6}>
          size=6
        </Column>
        <Column className="p-6 bg-secondary-lightest border">size=6</Column>
      </Row>
    </>
  );
}
```# Combobox

A combobox displays an input box combined with the option list.

### Code Examples

#### Combobox

```jsx
import { Spinner, Combobox, Label } from '@innovaccer/design-system';

() => {

  function useFetchOption() {
    const medicineList = [
      { label: 'Acetaminophen', value: 'Acetaminophen' },
      { label: 'Ibuprofen', value: 'Ibuprofen' },
      { label: 'Penicillin G', value: 'Penicillin G' },
      { label: 'Penbutolol', value: 'Penbutolol' },
      { label: 'Aminophenol', value: 'Aminophenol' },
      { label: 'Vancomycin', value: 'Vancomycin' },
    ];

    const getSearchedOptions = (options, searchTerm) => {
      const result = options.filter((option) => option.label.toLowerCase().startsWith(searchTerm.toLowerCase()));
      return result;
    };

    const fetchOptions = (searchTerm) => {
      const searchedOptions = searchTerm ? getSearchedOptions(medicineList, searchTerm) : medicineList;

      return new Promise((resolve) => {
        setTimeout(() => {
          resolve({
            options: searchedOptions,
          });
        }, 1000);
      });
    };
    
    return { fetchOptions };
  }

  const { fetchOptions } = useFetchOption();
  const [loading, setLoading] = React.useState(false);
  const [optionList, setOptionList] = React.useState([]);

  React.useEffect(() => {
    setLoading(true);
    fetchOptions().then((res) => {
      const { options } = res;
      setLoading(false);
      setOptionList(options);
    });
  }, []);

  const onChangeHandler = (item) => {
    console.log('selected option', item);

    setLoading(true);
    fetchOptions(item.label).then((res) => {
      const { options } = res;
      setLoading(false);
      setOptionList(options);
    });
  };

  const PopoverContent = ({loading, optionList}) => {
    if (loading) {
      return (
        <div className="d-flex align-items-center justify-content-center py-6">
          <Spinner />
        </div>
      );
    }

    if (optionList.length === 0) {
      return <></>;
    }

    return (
      <Combobox.List>
        {optionList.map((item, key) => {
          return (
            <Combobox.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Combobox.Option>
          );
        })}
      </Combobox.List>
    );
  };

  return (
    <div className="w-50">
      <Label withInput={true}>Drug Name</Label>
      <Combobox onChange={onChangeHandler} icon="search" placeholder="Enter drug name">
        <PopoverContent loading={loading} optionList={optionList} />
      </Combobox>
    </div>
  );
}
```


#### Combobox

```jsx
import { Label, Combobox, Text, Badge } from '@innovaccer/design-system';

() => {
  const providerList = [
    {
      name: 'Terry Wilson',
      position: 'Physicians of America/CIN Affiliates - East/Carcamo Pediatrics/Carcamo Pediatrics',
      id: '1144309823',
    },
    {
      name: 'Ted Warren',
      position: 'Physicians of America/CIN Affiliates - East/Carcamo Pediatrics/Carcamo Pediatrics',
      id: '1144379172',
    },
    {
      name: 'Tate Miles',
      position: 'Physicians of America/CIN Affiliates - East/Carcamo Pediatrics/Carcamo Pediatrics',
      id: '1144335826',
    },
  ];

  const [filterList, setFilterList] = React.useState(providerList);

  const onChangeHandler = (inputValue) => {
    console.log('inputValue', inputValue);
    const updatedList = providerList.filter((provider) =>
      provider.name.toLowerCase().startsWith(inputValue.label.toLowerCase())
    );

    setFilterList(updatedList);
  };

  return (
    <div>
      <Label withInput={true}>Provider Name</Label>
      <Combobox onChange={onChangeHandler} className="w-50" icon="search" placeholder='Enter provider name'>
        {filterList.length > 0 && (
          <Combobox.List>
            {filterList.map((item, key) => {
              return (
                <Combobox.Option key={key} option={{ label: item.name, value: item }}>
                  <div className="w-100">
                    <div className="d-flex justify-content-between align-items-center">
                      <Text>{item.name}</Text>
                      <Badge>{item.id}</Badge>
                    </div>
                    <Text size="small" appearance="subtle">
                      {item.position}
                    </Text>
                  </div>
                </Combobox.Option>
              );
            })}
          </Combobox.List>
        )}
      </Combobox>
    </div>
  );
}
```


#### Combobox

```jsx
import { Spinner, Combobox, Label } from '@innovaccer/design-system';

() => {
  function useFetchOption() {
    const medicineList = [
      { label: 'Acetaminophen', value: 'Acetaminophen' },
      { label: 'Ibuprofen', value: 'Ibuprofen' },
      { label: 'Penicillin G', value: 'Penicillin G' },
      { label: 'Penbutolol', value: 'Penbutolol' },
      { label: 'Aminophenol', value: 'Aminophenol' },
      { label: 'Vancomycin', value: 'Vancomycin' },
    ];

    const getSearchedOptions = (options, searchTerm) => {
      const result = options.filter((option) =>
        option.label.toLowerCase().startsWith(searchTerm.toLowerCase())
      );
      return result;
    };

    const fetchOptions = (searchTerm) => {
      const searchedOptions = searchTerm ? getSearchedOptions(medicineList, searchTerm) : medicineList;

      return new Promise((resolve) => {
        setTimeout(() => {
          resolve({
            options: searchedOptions,
          });
        }, 1000);
      });
    };

    return { fetchOptions };
  }

  const { fetchOptions } = useFetchOption();
  const [loading, setLoading] = React.useState(false);
  const [optionList, setOptionList] = React.useState([]);

  React.useEffect(() => {
    setLoading(true);
    fetchOptions(' ').then((res) => {
      const { options } = res;
      setLoading(false);
      setOptionList(options);
    });
  }, []);

  const onChangeHandler = (item) => {
    console.log('selected option', item);
    setLoading(true);
    if (!Array.isArray(item)) {
      fetchOptions(item.label).then((res) => {
        const { options } = res;
        setLoading(false);
        setOptionList(options);
      });
    }
  };

  const PopoverContent = ({ loading, optionList }) => {
    if (loading) {
      return (
        <div className="d-flex align-items-center justify-content-center py-6">
          <Spinner />
        </div>
      );
    }

    if (optionList.length === 0) {
      return <></>;
    }

    return (
      <Combobox.List>
        {optionList.map(
          (
            item, key
          ) => {
            return (
              <Combobox.Option key={key} option={{ label: item.label, value: item.value }}>
                {item.label}
              </Combobox.Option>
            );
          }
        )}
      </Combobox.List>
    );
  };

  return (
    <div className="w-50">
      <Label withInput={true}>Drug Name</Label>
      <Combobox
        multiSelect={false}
        onKeyDown={(ev) => console.log('onKeyDown :: ', ev)}
        onKeyUp={(ev) => console.log('onKeyUp :: ', ev)}
        onChange={onChangeHandler}
        icon="search"
        placeholder="Enter drug name"
      >
        <PopoverContent loading={loading} optionList={optionList} />
      </Combobox>
    </div>
  );
}
```


#### Combobox

```jsx
import { Label, Combobox } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Acetaminophen', value: 'Acetaminophen' },
    { label: 'Ibuprofen', value: 'Ibuprofen' },
    { label: 'Penicillin G', value: 'Penicillin G' },
    { label: 'Penbutolol', value: 'Penbutolol' },
    { label: 'Aminophenol', value: 'Aminophenol' },
    { label: 'Vancomycin', value: 'Vancomycin' },
  ];

  const [filterList, setFilterList] = React.useState([]);

  const onSearchHandler = (value) => {
    const newList = medicineList.filter((medicine) => medicine.label.toLowerCase().startsWith(value.toLowerCase()));
    setFilterList(newList);
    console.log('searchOption', value, newList);
  };

  const onChangeHandler = (selectedOption) => {
    const newList = medicineList.filter((medicine) => !isElementPresent(selectedOption, medicine.label));
    setFilterList(newList);
    console.log('input value', selectedOption);
  };

  const isElementPresent = (list, value) => {
    let result = false;
    list &&
      list.forEach((listItem) => {
        if (listItem.label === value) {
          result = true;
        }
      });
    return result;
  };

  return (
    <div>
      <Label withInput={true}>Drug Name</Label>
      <Combobox onSearch={onSearchHandler} onChange={onChangeHandler} multiSelect={true} clearButton={true}>
        {filterList.length > 0 && (
          <Combobox.List>
            {filterList.map((item, key) => {
              return (
                <Combobox.Option key={key} option={{ label: item.label, value: item.value }}>
                  {item.label}
                </Combobox.Option>
              );
            })}
          </Combobox.List>
        )}
      </Combobox>
    </div>
  );
}
```


#### Combobox

```jsx
import { Label, Combobox } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Acetaminophen', value: 'Acetaminophen' },
    { label: 'Ibuprofen', value: 'Ibuprofen' },
    { label: 'Penicillin G', value: 'Penicillin G' },
    { label: 'Penbutolol', value: 'Penbutolol' },
    { label: 'Aminophenol', value: 'Aminophenol' },
    { label: 'Vancomycin', value: 'Vancomycin' },
  ];
  const [filterList, setFilterList] = React.useState([]);

  const [selectedOption, setSelectedOption] = React.useState([
    { label: 'Penicillin G', value: 'Penicillin G' },
    { label: 'Penbutolol', value: 'Penbutolol' },
  ]);

  const onSearchHandler = (value) => {
    const newList = medicineList.filter((medicine) => medicine.label.toLowerCase().startsWith(value.toLowerCase()));
    
    setFilterList(newList);
    console.log('searchOption', value, newList);
  };

  const onChangeHandler = (selectedOption) => {
    const newList = medicineList.filter((medicine) => !isElementPresent(selectedOption, medicine.label));
    setFilterList(newList);
    setSelectedOption(selectedOption);
    console.log('input value', selectedOption);
  };

  const isElementPresent = (list, value) => {
    let result = false;
    list.forEach((listItem) => {
      if (listItem && listItem.label === value) {
        result = true;
      }
    });
    return result;
  };

  return (
    <div>
      <Label withInput={true}>Drug Name</Label>
      <Combobox
        chipValue={selectedOption}
        onSearch={onSearchHandler}
        onChange={onChangeHandler}
        multiSelect={true}
        clearButton={true}
      >
        {filterList.length > 0 && (
          <Combobox.List>
            {filterList.map((item, key) => {
              return (
                <Combobox.Option key={key} option={{ label: item.label, value: item.value }}>
                  {item.label}
                </Combobox.Option>
              );
            })}
          </Combobox.List>
        )}
      </Combobox>
    </div>
  );
}
```


#### Combobox

```jsx
import { Tooltip, Combobox, Text, Label } from '@innovaccer/design-system';

() => {

  /*
    .Combobox-outerWrapper {
      max-width: var(--spacing-9);
    }
  */

  const barrierList = [
    { label: 'Health issues', value: 'Health issues' },
    { label: 'Lack of employment', value: 'Lack of employment' },
    {
      label: 'Lack of readiness to change with environment',
      value: 'Lack of readiness to change with environment',
    },
    { label: 'Lack of understanding', value: 'Lack of understanding' },
    { label: 'Lack of benefits', value: 'Lack of benefits' },
    { label: 'No housing', value: 'No housing' },
  ];

  const [filterList, setFilterList] = React.useState(barrierList);

  const onChangeHandler = (inputValue) => {
    console.log('inputValue', inputValue);
    const updatedList = barrierList.filter((medicine) =>
      medicine.label.toLowerCase().startsWith(inputValue.label.toLowerCase())
    );

    setFilterList(updatedList);
  };

  const ComboboxItem = ({ item }) => {
    const [showTooltip, setShowTooltip] = React.useState(false);
    const elementRef = React.useRef(null);

    return (
      <Tooltip showOnTruncation={true} tooltip={item.label} elementRef={elementRef} open={showTooltip}>
        <Combobox.Option
          option={{ label: item.label, value: item.value }}
          onFocus={() => {
            setShowTooltip(true);
          }}
          onBlur={() => {
            setShowTooltip(false);
          }}
        >
          <Text ref={elementRef} className="ellipsis--noWrap d-inline-block w-100">
            {item.label}
          </Text>
        </Combobox.Option>
      </Tooltip>
    );
  };

  return (
    <div className="Combobox-outerWrapper">
      <Label withInput={true}>Barriers</Label>
      <Combobox onChange={onChangeHandler} placeholder="Enter barriers">
        {filterList.length > 0 && (
          <Combobox.List>
            {filterList.map((item, key) => {
              return <ComboboxItem item={item} key={key} />;
            })}
          </Combobox.List>
        )}
      </Combobox>
    </div>
  );
}
```


#### Combobox

```jsx
import { Label, Combobox } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Acetaminophen', value: 'Acetaminophen' },
    { label: 'Ibuprofen', value: 'Ibuprofen' },
    { label: 'Penicillin G', value: 'Penicillin G' },
    { label: 'Penbutolol', value: 'Penbutolol' },
    { label: 'Aminophenol', value: 'Aminophenol' },
    { label: 'Vancomycin', value: 'Vancomycin' },
  ];

  const [filterList, setFilterList] = React.useState([]);
  const [selectedOption, setSelectedOption] = React.useState({ label: 'Acetaminophen', value: 'Acetaminophen' });

  const onChangeHandler = (item) => {
    const newList = medicineList.filter((medicine) =>
      medicine.label.toLowerCase().startsWith(item.label.toLowerCase())
    );
    setFilterList(newList);
    setSelectedOption(item);
    console.log('item', item);
  };

  return (
    <div>
      <Label withInput={true}>Drug Name</Label>
      <Combobox icon="search" value={selectedOption} onChange={onChangeHandler}>
        {filterList.length > 0 && (
          <Combobox.List>
            {filterList.map((item, key) => {
              const option = { label: item.label, value: item.value };
              return (
                <Combobox.Option key={key} option={option}>
                  {item.label}
                </Combobox.Option>
              );
            })}
          </Combobox.List>
        )}
      </Combobox>
    </div>
  );
}
```


#### Combobox

```jsx
import { Label, Combobox } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Acetaminophen', value: 'Acetaminophen' },
    { label: 'Ibuprofen', value: 'Ibuprofen' },
    { label: 'Penicillin G', value: 'Penicillin G' },
    { label: 'Penbutolol', value: 'Penbutolol' },
    { label: 'Aminophenol', value: 'Aminophenol' },
    { label: 'Vancomycin', value: 'Vancomycin' },
  ];

  const [filterList, setFilterList] = React.useState(medicineList);
  const sizes = ['tiny', 'regular', 'large'];

  const onChangeHandler = (inputValue) => {
    console.log(' inputValue', inputValue);
    const updatedList = medicineList.filter((medicine) =>
      medicine.label.toLowerCase().startsWith(inputValue.label.toLowerCase())
    );

    setFilterList(updatedList);
  };

  return (
    <div className="d-flex align-items-center justify-content-between">
      {sizes.map((size) => {
        return (
          <div key={size}>
            <Label withInput={true}>Drug Name</Label>
            <Combobox onChange={onChangeHandler} placeholder="Enter drug name" size={size}>
              {filterList.length > 0 && (
                <Combobox.List>
                  {filterList.map((item, key) => {
                    return (
                      <Combobox.Option key={key} option={{ label: item.label, value: item.value }}>
                        {item.label}
                      </Combobox.Option>
                    );
                  })}
                </Combobox.List>
              )}
            </Combobox>
          </div>
        );
      })}
    </div>
  );
}
```


#### Combobox

```jsx
import { Label, Combobox } from '@innovaccer/design-system';

() => {
  const barrierList = [
    { label: 'Health issues', value: 'Health issues' },
    { label: 'Lack of employment', value: 'Lack of employment' },
    { label: 'Lack of readiness to change', value: 'Lack of readiness to change' },
    { label: 'Lack of understanding', value: 'Lack of understanding' },
    { label: 'Lack of benefits', value: 'Lack of benefits' },
    { label: 'No housing', value: 'No housing' },
  ];

  const [filterList, setFilterList] = React.useState(barrierList);

  const onChangeHandler = (inputValue) => {
    console.log(' inputValue', inputValue);
    const updatedList = barrierList.filter((medicine) =>
      medicine.label.toLowerCase().startsWith(inputValue.label.toLowerCase())
    );

    setFilterList(updatedList);
  };

  return (
    <div>
      <Label withInput={true}>Barriers</Label>
      <Combobox onChange={onChangeHandler} className="w-50" placeholder="Enter barriers">
        {filterList.length > 0 && (
          <Combobox.List>
            {filterList.map((item, key) => {
              return (
                <Combobox.Option key={key} option={{ label: item.label, value: item.value }}>
                  {item.label}
                </Combobox.Option>
              );
            })}
          </Combobox.List>
        )}
      </Combobox>
    </div>
  );
}
```


#### Combobox

```jsx
import { Label, Combobox, HelpText } from '@innovaccer/design-system';

() => {
  const barrierList = [
    { label: 'Health issues', value: 'Health issues' },
    { label: 'Lack of employment', value: 'Lack of employment' },
    { label: 'Lack of readiness to change', value: 'Lack of readiness to change' },
    { label: 'Lack of understanding', value: 'Lack of understanding' },
    { label: 'Lack of benefits', value: 'Lack of benefits' },
    { label: 'No housing', value: 'No housing' },
  ];

  const [filterList, setFilterList] = React.useState(barrierList);

  const onChangeHandler = (inputValue) => {
    console.log(' inputValue', inputValue);
    const updatedList = barrierList.filter((medicine) =>
      medicine.label.toLowerCase().startsWith(inputValue.label.toLowerCase())
    );

    setFilterList(updatedList);
  };

  return (
    <div>
      <Label withInput={true}>Barriers</Label>
      <Combobox onChange={onChangeHandler} className="w-50" error={true}>
        {filterList.length > 0 && (
          <Combobox.List>
            {filterList.map((item, key) => {
              return (
                <Combobox.Option key={key} option={{ label: item.label, value: item.value }}>
                  {item.label}
                </Combobox.Option>
              );
            })}
          </Combobox.List>
        )}
      </Combobox>
      <HelpText error={true} message="Please choose a valid option" />
    </div>
  );
}
```# ControlledDropdown



### Code Examples

#### Controlled Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const dropdownOptions =  [];
  for (let i = 1; i <= 100; i++) {
    dropdownOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      group: i >= 1 && i <= 40 ? 'Group 1' : 'Group 2',
      icon: 'events',
      subInfo: 'subInfo',
    });
  }

  const [selected, setSelected] = React.useState([dropdownOptions[3]]);
  const [open, setOpen] = React.useState(false);

  const getSearchedOptions = (options, searchTerm) => {
    const result = options.filter((option) => option.label.toLowerCase().includes(searchTerm.toLowerCase()));
    return result;
  };

  const fetchOptions = (searchTerm) => {
    const searchedOptions = searchTerm ? getSearchedOptions(dropdownOptions, searchTerm) : dropdownOptions;
    return new Promise(resolve => {
      this.window.setTimeout(() => {
        resolve({
          searchTerm,
          options: searchedOptions,
          count: searchedOptions.length,
        });
      }, 1000);
    });
  };

  const onChangeHandler = (selectedValues) => {
    console.log(selectedValues);
  };

  const onPopperToggle = (popperIsOpen, type) => {
    setOpen(popperIsOpen);
    console.log(`type: ${type}`);
  }

  const onUpdate = (type, options, recentSelected) => {
    switch (type) {
      case 'apply-selected':
        setSelected(recentSelected);
        return;
      case 'cancel-selected':
        console.log('cancel-clicked');
      default:
        return;
    }
  };

  const onClose = (values) => {
    console.log(`dropdown closed with selected values: ${values}`)
  };

  return (
    <div className="w-25">
      <Text weight="strong">{'Options > 50'}</Text><br /><br />
      <Dropdown
        fetchOptions={fetchOptions}
        onPopperToggle={onPopperToggle}
        onUpdate={onUpdate}
        selected={selected}
        onChange={onChangeHandler}
        withCheckbox={true}
        showApplyButton={true}
        open={open}
        onClose={onClose}
      />
    </div>
  );
}
```


#### Controlled Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const dropdownOptions =  [];
  for (let i = 1; i <= 100; i++) {
    dropdownOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      group: i >= 1 && i <= 40 ? 'Group 1' : 'Group 2',
      icon: 'events',
      subInfo: 'subInfo',
    });
  }

  const [selected, setSelected] = React.useState([dropdownOptions[3]]);
  const [open, setOpen] = React.useState(false);

  const onChangeHandler = (selectedValues) => {
    console.log(selectedValues);
  };

  const onUpdate = (type, options, recentSelected) => {
    switch (type) {
      case 'apply-selected':
        setOpen(!open);
        setSelected(recentSelected);
        return;
      case 'cancel-selected':
        setOpen(!open);
        return action('cancel event triggered')();
      default:
        return;
    }
  };

  const onPopperToggle = (isPopperOpen) => {
    setOpen(isPopperOpen);
  };

  return (
    <div className="w-25">
      <Text weight="strong">{'Options <= 50'}</Text><br /><br />
      <Dropdown
        options={dropdownOptions.slice(0, 50)}
        onPopperToggle={onPopperToggle}
        onUpdate={onUpdate}
        selected={selected}
        onChange={onChangeHandler}
        withCheckbox={true}
        showApplyButton={true}
        open={open}
      />
    </div>
  );
}
```


#### Controlled Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const dropdownOptions =  [];
  for (let i = 1; i <= 100; i++) {
    dropdownOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      group: i >= 1 && i <= 40 ? 'Group 1' : 'Group 2',
      icon: 'events',
      subInfo: 'subInfo',
    });
  }

  const [selected, setSelected] = React.useState([dropdownOptions[3]]);
  const [open, setOpen] = React.useState(false);

  const getSearchedOptions = (options, searchTerm) => {
    const result = options.filter((option) => option.label.toLowerCase().includes(searchTerm.toLowerCase()));
    return result;
  };

  const fetchOptions = (searchTerm) => {
    const searchedOptions = searchTerm ? getSearchedOptions(dropdownOptions, searchTerm) : dropdownOptions;
    return new Promise(resolve => {
      this.window.setTimeout(() => {
        resolve({
          searchTerm,
          options: searchedOptions,
          count: searchedOptions.length,
        });
      }, 1000);
    });
  };

  const onChangeHandler = (selectedValues) => {
    console.log(selectedValues);
  };

  const onUpdate = (_type, option) => {
    this.window.setTimeout(() => {
      setSelected([option]);
    }, 2000);
  };

  const onPopperToggle = (updatedOpen, type) => {
    console.log(type)
    setOpen(updatedOpen);
  }

  const onClose = (values) => {
    console.log(values);
  }

  return (
    <div className="w-25">
      <Dropdown
        fetchOptions={fetchOptions}
        onUpdate={onUpdate}
        selected={selected}
        onChange={onChangeHandler}
        onPopperToggle={onPopperToggle}
        onClose={onClose}
        open={open}
      />
    </div>
  );
}
```# DatePicker

Date picker is used for selecting or entering a date value.

### Code Examples

#### Components DatePicker DatePicker All

```jsx
import { DatePicker, Card } from '@innovaccer/design-system';

() => {
  const withInput = false;

  const open = false;

  const closeOnSelect = true;

  const inputFormat = 'dd-mm-yyyy';

  const outputFormat = 'yyyy-mm-dd';

  const dateValue = undefined;

  const view = 'month';

  const firstDayOfWeek = 'sunday';

  const disabledBefore = new Date('Jan 20 2015');

  const disabledAfter = new Date('Jan 20 2028');

  const jumpView = true;

  const yearNav = -1;

  const monthNav = -1;

  const attr = {};
  if (disabledBefore) attr.disabledBefore = disabledBefore;
  if (disabledAfter) attr.disabledAfter = disabledAfter;
  if (yearNav !== -1) attr.yearNav = yearNav;
  if (monthNav !== -1) attr.monthNav = monthNav;

  if (withInput) {
    return (
      <DatePicker
        withInput={withInput}
        closeOnSelect={closeOnSelect}
        open={open}
        inputFormat={inputFormat}
        outputFormat={outputFormat}
        jumpView={jumpView}
        date={dateValue}
        onDateChange={(currDate) => action(`on date change : ${currDate}`)()}
        view={view}
        firstDayOfWeek={firstDayOfWeek}
        {...attr}
      />
    );
  }
  return (
    <Card className="d-inline-flex" shadow="light">
      <DatePicker
        withInput={withInput}
        inputFormat={inputFormat}
        outputFormat={outputFormat}
        jumpView={jumpView}
        date={dateValue}
        onDateChange={(currDate) => action(`on date change : ${currDate}`)()}
        view={view}
        firstDayOfWeek={firstDayOfWeek}
        {...attr}
      />
    </Card>
  );
}
```


#### DatePicker

```jsx
import { Card, DatePicker } from '@innovaccer/design-system';

() => {
  const values = ['year', 'month', 'date'];

  return (
    <div className="d-flex">
      {values.map((v, index) => (
        <div key={index} className="mr-5">
          <Card className="d-inline-flex" shadow="light">
            <DatePicker date={new Date(2023, 5, 1)} view={v} />
          </Card>
        </div>
      ))}
    </div>
  );
}
```


#### Components DatePicker DatePicker Variants With Input

```jsx
import { DatePicker } from '@innovaccer/design-system';

() => {
  const dateValue = undefined;

  const inputFormat = 'mm/dd/yyyy';

  const outputFormat = 'yyyy/mm/dd';

  const view = 'date';

  const firstDayOfWeek = 'saturday';

  const disabledBefore = new Date('Jan 20 2015');

  const disabledAfter = new Date('Jan 20 2028');

  const jumpView = true;

  const yearNav = -1;

  const monthNav = -1;

  const closeOnSelect = true;

  const attr = {};
  if (disabledBefore) attr.disabledBefore = disabledBefore;
  if (disabledAfter) attr.disabledAfter = disabledAfter;
  if (yearNav !== -1) attr.yearNav = yearNav;
  if (monthNav !== -1) attr.monthNav = monthNav;

  return (
    <div className="w-25">
      <DatePicker
        withInput={true}
        closeOnSelect={closeOnSelect}
        inputFormat={inputFormat}
        outputFormat={outputFormat}
        jumpView={jumpView}
        date={dateValue}
        onDateChange={(currDate, currValue) => {
          action(`on date change : ${currDate} --- ${currValue}`)();
        }}
        view={view}
        firstDayOfWeek={firstDayOfWeek}
        inputOptions={{
          required: true,
        }}
        {...attr}
      />
    </div>
  );
}
```# DateRangePicker



### Code Examples

#### Components DatePicker DateRangePicker All

```jsx
import { DateRangePicker, Card } from '@innovaccer/design-system';

() => {
  const withInput = false;

  const open = false;

  const monthsInView = withInput ? 2 : 1;

  const inputFormat = 'dd/mm/yyyy';

  const outputFormat = 'mm/dd/yyyy';

  const startDate = new Date('Jun 20 2023');

  const endDate = new Date('Jun 27 2023');

  const view = 'month';

  const rangeLimit = 0;

  const firstDayOfWeek = 'thursday';

  const disabledBefore = new Date('Jan 20 2015');

  const disabledAfter = new Date('Jan 20 2028');

  const jumpView = true;

  const yearNav = -1;

  const monthNav = -1;

  const attr = {};
  if (disabledBefore) attr.disabledBefore = disabledBefore;
  if (disabledAfter) attr.disabledAfter = disabledAfter;
  if (rangeLimit) attr.rangeLimit = rangeLimit;
  if (yearNav !== -1) attr.yearNav = yearNav;
  if (monthNav !== -1) attr.monthNav = monthNav;

  if (withInput) {
    return (
      <DateRangePicker
        withInput={withInput}
        open={open}
        monthsInView={monthsInView}
        inputFormat={inputFormat}
        outputFormat={outputFormat}
        jumpView={jumpView}
        startDate={startDate}
        endDate={endDate}
        onRangeChange={(sDate, eDate, sValue, eValue) =>
          action(`on range change: ${sDate} - ${eDate} ---- ${sValue} - ${eValue}`)()
        }
        view={view}
        firstDayOfWeek={firstDayOfWeek}
        {...attr}
      />
    );
  }
  return (
    <Card className="d-inline-flex" shadow="light">
      <DateRangePicker
        withInput={withInput}
        monthsInView={monthsInView}
        jumpView={jumpView}
        startDate={startDate}
        endDate={endDate}
        onRangeChange={(sDate, eDate, sValue, eValue) =>
          action(`on range change: ${sDate} - ${eDate} ---- ${sValue} - ${eValue}`)()
        }
        view={view}
        firstDayOfWeek={firstDayOfWeek}
        {...attr}
      />
    </Card>
  );
}
```


#### DateRangePicker

```jsx
import { Card, DateRangePicker } from '@innovaccer/design-system';

() => {
  // to freeze the object for typescript

  return (
    <div className="d-flex flex-column">
      {Array.from([1, 2, 3], (x, key) => (
        <div key={key} className="mt-5 align-self-start">
          <Card className="d-inline-flex" shadow="light">
            <DateRangePicker
              monthsInView={x}
              startDate={new Date(2023, 11, 3)}
              endDate={new Date(2023, x - 2, 11)}
              yearNav={2023}
              monthNav={11}
            />
          </Card>
        </div>
      ))}
    </div>
  );
}
```


#### DateRangePicker

```jsx
import { Card, DateRangePicker } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex mr-9">
      <Card className="d-inline-flex" shadow="light">
        <DateRangePicker
          startDate={new Date(2023, 2, 3)}
          endDate={new Date(2023, 2, 11)}
          rangeLimit={7}
          yearNav={2023}
          monthNav={2}
        />
      </Card>
    </div>
  );
}
```


#### DateRangePicker

```jsx
import { Card, DateRangePicker } from '@innovaccer/design-system';

() => {
  const values = ['year', 'month', 'date'];

  return (
    <div className="d-flex">
      {values.map((v, index) => (
        <div className="mr-9" key={index}>
          <Card className="d-inline-flex" shadow="light">
            <DateRangePicker
              startDate={new Date(2023, 2, 3)}
              endDate={new Date(2023, 2, 11)}
              view={v}
              yearNav={2023}
              monthNav={2}
            />
          </Card>
        </div>
      ))}
    </div>
  );
}
```


#### Components DatePicker DateRangePicker Variants With Input

```jsx
import { DateRangePicker } from '@innovaccer/design-system';

() => {
  const monthsInView = 2;

  const startDate = new Date('Jan 12 2023');

  const endDate = new Date('Jan 20 2023');

  const inputFormat = 'mm-dd-yyyy';

  const outputFormat = 'yyyy-mm-dd';

  const view = 'year';

  const firstDayOfWeek = 'monday';

  const disabledBefore = new Date('Jan 20 2015');

  const disabledAfter = new Date('Jan 20 2028');

  const jumpView = true;

  const yearNav = -1;

  const monthNav = -1;

  const attr = {};
  if (disabledBefore) attr.disabledBefore = disabledBefore;
  if (disabledAfter) attr.disabledAfter = disabledAfter;
  if (yearNav !== -1) attr.yearNav = yearNav;
  if (monthNav !== -1) attr.monthNav = monthNav;

  return (
    <div className="w-75">
      <DateRangePicker
        withInput={true}
        startDate={startDate}
        endDate={endDate}
        inputFormat={inputFormat}
        outputFormat={outputFormat}
        jumpView={jumpView}
        onRangeChange={(sDate, eDate, sValue, eValue) =>
          action(`on range change: ${sDate} - ${eDate} ---- ${sValue} - ${eValue}`)()
        }
        view={view}
        firstDayOfWeek={firstDayOfWeek}
        monthsInView={monthsInView}
        startInputOptions={{
          required: true,
        }}
        endInputOptions={{
          required: true,
        }}
        {...attr}
      />
    </div>
  );
}
```


#### Components DatePicker DateRangePicker Variants With Reverse Selection

```jsx
import { DateRangePicker } from '@innovaccer/design-system';

() => {
  const monthsInView = 2;

  const startDate = new Date('Jan 12 2023');

  const endDate = new Date('Jan 20 2023');

  const inputFormat = 'mm-dd-yyyy';

  const outputFormat = 'yyyy-mm-dd';

  const view = 'year';

  const firstDayOfWeek = 'monday';

  const disabledBefore = new Date('Jan 20 2015');

  const disabledAfter = new Date('Jan 20 2028');

  const jumpView = true;

  const yearNav = -1;

  const monthNav = -1;

  const attr = {};
  if (disabledBefore) attr.disabledBefore = disabledBefore;
  if (disabledAfter) attr.disabledAfter = disabledAfter;
  if (yearNav !== -1) attr.yearNav = yearNav;
  if (monthNav !== -1) attr.monthNav = monthNav;

  return (
    <div className="w-75">
      <DateRangePicker
        allowReverseSelection={true}
        withInput={true}
        startDate={startDate}
        endDate={endDate}
        inputFormat={inputFormat}
        outputFormat={outputFormat}
        jumpView={jumpView}
        onRangeChange={(sDate, eDate, sValue, eValue) =>
          action(`on range change: ${sDate} - ${eDate} ---- ${sValue} - ${eValue}`)()
        }
        view={view}
        firstDayOfWeek={firstDayOfWeek}
        monthsInView={monthsInView}
        startInputOptions={{
          required: true,
        }}
        endInputOptions={{
          required: true,
        }}
        {...attr}
      />
    </div>
  );
}
```


#### Components DatePicker DateRangePicker Variants With Single Input

```jsx
import { DateRangePicker } from '@innovaccer/design-system';

() => {
  const monthsInView = 2;

  const startDate = new Date('Jan 20 2023');

  const endDate = new Date('Jan 28 2023');

  const inputFormat = 'dd/mm/yyyy';

  const outputFormat = 'mm-dd-yyyy';

  const view = 'date';

  const firstDayOfWeek = 'monday';

  const disabledBefore = new Date('Jan 20 2015');

  const disabledAfter = new Date('Jan 20 2028');

  const jumpView = true;

  const yearNav = -1;

  const monthNav = -1;

  const open = false;

  const attr = {};
  if (disabledBefore) attr.disabledBefore = disabledBefore;
  if (disabledAfter) attr.disabledAfter = disabledAfter;
  if (yearNav !== -1) attr.yearNav = yearNav;
  if (monthNav !== -1) attr.monthNav = monthNav;

  return (
    <div className="w-50">
      <DateRangePicker
        withInput={true}
        singleInput={true}
        startDate={startDate}
        endDate={endDate}
        inputFormat={inputFormat}
        outputFormat={outputFormat}
        jumpView={jumpView}
        onRangeChange={(sDate, eDate, sValue, eValue) =>
          action(`on range change: ${sDate} - ${eDate} ---- ${sValue} - ${eValue}`)()
        }
        view={view}
        firstDayOfWeek={firstDayOfWeek}
        monthsInView={monthsInView}
        inputOptions={{
          required: true,
          label: 'Date',
        }}
        {...attr}
        open={open}
      />
    </div>
  );
}
```


#### Components DatePicker DateRangePicker Variants With Single Input And Reverse Selection

```jsx
import { DateRangePicker } from '@innovaccer/design-system';

() => {
  const monthsInView = 2;

  const startDate = new Date('Jan 20 2023');

  const endDate = new Date('Jan 28 2023');

  const inputFormat = 'dd/mm/yyyy';

  const outputFormat = 'mm-dd-yyyy';

  const view = 'date';

  const firstDayOfWeek = 'monday';

  const disabledBefore = new Date('Jan 20 2015');

  const disabledAfter = new Date('Jan 20 2028');

  const jumpView = true;

  const yearNav = -1;

  const monthNav = -1;

  const open = false;

  const attr = {};
  if (disabledBefore) attr.disabledBefore = disabledBefore;
  if (disabledAfter) attr.disabledAfter = disabledAfter;
  if (yearNav !== -1) attr.yearNav = yearNav;
  if (monthNav !== -1) attr.monthNav = monthNav;

  return (
    <div className="w-50">
      <DateRangePicker
        allowReverseSelection={true}
        withInput={true}
        singleInput={true}
        startDate={startDate}
        endDate={endDate}
        inputFormat={inputFormat}
        outputFormat={outputFormat}
        jumpView={jumpView}
        onRangeChange={(sDate, eDate, sValue, eValue) =>
          action(`on range change: ${sDate} - ${eDate} ---- ${sValue} - ${eValue}`)()
        }
        view={view}
        firstDayOfWeek={firstDayOfWeek}
        monthsInView={monthsInView}
        inputOptions={{
          required: true,
          label: 'Date',
        }}
        {...attr}
        open={open}
      />
    </div>
  );
}
```# Dialog



### Code Examples

#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    dimension: 'large',
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Basic',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    dimension: 'medium',
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Basic',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    dimension: 'small',
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Basic',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    primaryButtonAppearance: 'alert',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Basic',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    primaryButtonAppearance: 'basic',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Basic',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    primaryButtonAppearance: 'primary',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Basic',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    primaryButtonAppearance: 'success',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Basic',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    primaryButtonAppearance: 'transparent',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Basic',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    secondaryButtonAppearance: 'alert',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Secondary',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    secondaryButtonAppearance: 'basic',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Secondary',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    secondaryButtonAppearance: 'primary',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Secondary',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    secondaryButtonAppearance: 'success',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Secondary',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```


#### Dialog

```jsx
import { Paragraph, Button, Dialog } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const options = {
    open,
    onClose,
    icon: 'pan_tool',
    heading: 'Heading',
    title: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
    secondaryButtonAppearance: 'transparent',
    primaryButtonLabel: 'Primary',
    secondaryButtonLabel: 'Secondary',
  };

  return (
    <div>
      <Paragraph>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. <br />
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <br />
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. <br />
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />
        <Button appearance="primary" onClick={() => setOpen(true)}>Open</Button>
      </Paragraph>
      <Dialog {...options} />
    </div>
  );
}
```# Divider



### Code Examples

#### Components Divider All

```jsx
import { Row, Column, Card, CardBody, Heading, Divider, Text } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column size="10">
        <Card shadow="none">
          <CardBody className="p-0">
            <Row className="py-4 px-6">
              <Heading>Assessment Report</Heading>
            </Row>

            <Divider appearance="header" />
            <Row>
              <Column>
                <div className="p-6">
                  <Heading size="s">Select Assessment</Heading>
                </div>
                <Divider />
                <div className="pl-6">
                  <div className="py-4">
                    <Text>Functional Assessment - Initial</Text>
                  </div>
                  <Divider />

                  <div className="py-4">
                    <Text>Social Influence of Health</Text>
                  </div>
                  <Divider />

                  <div className="py-4">
                    <Text>Social Determinants of Health</Text>
                  </div>
                  <Divider />

                  <div className="py-4">
                    <Text>Functional Assessment - Discharge</Text>
                  </div>
                </div>
              </Column>
              <Divider vertical={true} />

              <Column>
                <div className="p-6">
                  <Text appearance="disabled">MSSP - Track 3</Text>
                  <br />
                  <Text small={true}>Medicare</Text>
                  <br />
                  <div className="pt-6">
                    <Text appearance="disabled" small={true}>
                      Subscriber
                    </Text>
                    <br />
                    <Text appearance="disabled">LAWSON, JOY (Self)</Text>
                    <br />
                    <Text weight="medium">ZGP123456789</Text>
                  </div>
                </div>
                <Divider />
                <Row className="p-6">
                  <Column>
                    <Text appearance="disabled" small={true}>
                      Last attr:
                    </Text>
                    <Text className="ml-3" small={true}>
                      04/19
                    </Text>
                  </Column>
                  <Column>
                    <Text appearance="disabled" small={true}>
                      Plan ID:
                    </Text>
                    <Text className="ml-3" small={true}>
                      040
                    </Text>
                  </Column>
                </Row>
              </Column>
            </Row>
          </CardBody>
        </Card>
      </Column>
    </Row>
  );
}
```


#### Components Divider Horizontal All

```jsx
import { Row, Column, Divider, Text } from '@innovaccer/design-system';

() => {
  return (
    <div>
      <Row>
        <Column className="p-6">
          <Divider />
          <br />
          <Text weight="strong">Basic Divider</Text>
        </Column>

        <Column className="p-6">
          <Divider appearance="header" />
          <br />
          <Text weight="strong">Header Divider</Text>
        </Column>
      </Row>
    </div>
  );
}
```


#### Components Divider Horizontal Basic Divider In Card

```jsx
import { Row, Column, Card, CardBody, Text, Badge, Divider } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column size="9">
        <Card className="pt-6" shadow="none">
          <CardBody>
            <div className="d-flex justify-content-between">
              <Text appearance="disabled">MSSP - Track 3</Text>
              <Badge appearance="success" subtle={true}>
                ACTIVE
              </Badge>
            </div>
            <br />
            <Text small={true}>Medicare</Text>
            <br />
            <div className="py-6">
              <Text appearance="disabled" small={true}>
                Subscriber
              </Text>
              <br />
              <Text appearance="disabled">LAWSON, JOY (Self)</Text>
              <br />
              <Text weight="medium">ZGP123456789</Text>
            </div>
          </CardBody>

          {/* Horizontal Divider */}
          <Divider />

          <CardBody className="py-4">
            <Row>
              <Column>
                <Text appearance="disabled" small={true}>
                  Last attr:
                </Text>
                <Text className="ml-3" small={true}>
                  04/19
                </Text>
              </Column>
              <Column>
                <Text appearance="disabled" small={true}>
                  Plan ID:
                </Text>
                <Text className="ml-3" small={true}>
                  040
                </Text>
              </Column>
              <Column>
                <Text appearance="disabled" small={true}>
                  Payer ID:
                </Text>
                <Text className="ml-3" small={true}>
                  001
                </Text>
              </Column>
            </Row>
          </CardBody>
        </Card>
      </Column>
    </Row>
  );
}
```


#### Components Divider Horizontal Header Divider In Card

```jsx
import { Row, Column, Card, CardBody, Heading, Divider, Text, Radio } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column size="6">
        <Card className="pb-6" shadow="none">
          <CardBody className="p-0">
            <Row className="p-4">
              <Heading size="s">Section 1</Heading>
            </Row>

            <Divider appearance="header" />

            <div className="px-4 pt-5">
              <Text weight="strong">1. Little interest or pleasure in doing things.</Text>
              <br />
              <Column className="px-4 mt-5">
                <Radio defaultChecked={true} label="Not at all" name="section" size="regular" value="Not at all" />
                <Radio label="Several Days" name="section" size="regular" value="Several Days" />
                <Radio label="More than half the days" name="section" size="regular" value="More than half days" />
              </Column>
            </div>
          </CardBody>
        </Card>
      </Column>
    </Row>
  );
}
```


#### Components Divider Indented

```jsx
import { Row, Column, Heading, Card, CardBody, Input, Divider, Text } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column size="8">
        <Heading size="m">Select assessment</Heading>
        <Card>
          <CardBody className="p-0">
            <Row className="p-6">
              <Column size={8}>
                <Input className="w-25" icon="search" name="input" placeholder="Search" />
              </Column>
            </Row>

            <Divider appearance="header" />

            <div className="pl-6">
              <div className="py-6">
                <Text>Functional Assessment - Initial</Text>
              </div>
              <Divider />

              <div className="py-6">
                <Text>Functional Assessment - Discharge</Text>
              </div>
              <Divider />

              <div className="py-6">
                <Text>Social Influence of Health</Text>
              </div>
              <Divider />

              <div className="py-6">
                <Text>Social Determinants of Health</Text>
              </div>
            </div>
          </CardBody>
        </Card>
      </Column>
    </Row>
  );
}
```


#### Components Divider Vertical

```jsx
import { Row, Column, Card, CardBody, Text, Divider, Radio } from '@innovaccer/design-system';

() => {
  return (
    <Row>
      <Column size="10">
        <Card shadow="none">
          <CardBody className="p-0">
            <Row>
              <Column className="p-6">
                <Text appearance="disabled">MSSP - Track 3</Text>
                <br />
                <Text small={true}>Medicare</Text>
                <br />
                <div className="pt-6">
                  <Text appearance="disabled" small={true}>
                    Subscriber
                  </Text>
                  <br />
                  <Text appearance="disabled">LAWSON, JOY (Self)</Text>
                  <br />
                  <Text weight="medium">ZGP123456789</Text>
                </div>
              </Column>

              <Divider vertical={true} />

              <Column className="p-6">
                <div>
                  <Text weight="strong">1. Little interest or pleasure in doing things.</Text>
                  <br />
                  <Column className="px-4 mt-5">
                    <Radio defaultChecked={true} label="Not at all" name="section" size="regular" value="Not at all" />
                    <Radio label="Several Days" name="section" size="regular" value="Several Days" />
                    <Radio label="More than half the days" name="section" size="regular" value="More than half days" />
                  </Column>
                </div>
              </Column>
            </Row>
          </CardBody>
        </Card>
      </Column>
    </Row>
  );
}
```# Dropdown



### Code Examples

#### Dropdown

```jsx
import { Label, Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Male',
      value: 'Male',
    },
    {
      label: 'Female',
      value: 'Female',
    },
    {
      label: 'Transgender',
      value: 'Transgender',
    },
    {
      label: 'Others',
      value: 'Others',
    },
  ];
  return (
    <div className="mb-10 w-25">
      <Label withInput={true}>Gender</Label>
      <Dropdown options={options} searchPlaceholder="Search Gender" withSearch={true} />
    </div>
  );
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Edit',
      value: 'edit',
    },
    {
      label: 'Export',
      value: 'export',
    },
    {
      label: 'Delete',
      value: 'delete',
    },
  ];
  return (
    <div className="d-flex w-50">
      <Dropdown options={options} menu={true} className="mr-5" align="right" maxWidth={130} />
      <Dropdown options={options} menu={true} align="left" className="mr-5" maxWidth={130} />
    </div>
  );
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    { label: 'Below 18', subInfo: 'People below 18 years old', value: 'below_18', optionType: 'WITH_META' },
    { label: '19 - 35', subInfo: 'People 19-35 years old', value: '19-35', optionType: 'WITH_META' },
    { label: '36 - 55', subInfo: 'People 36-55 years old', value: '36-55', optionType: 'WITH_META' },
    { label: '56 and above', subInfo: 'People above 56 years old', value: '56_above', optionType: 'WITH_META' },
  ];
  return (
    <div className="d-flex w-50">
      <Dropdown options={options} menu={true} className="mr-5" align="right" />
      <Dropdown options={options} menu={true} className="mr-5" align="right" />
    </div>
  );
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Below 18',
      value: 'below_18',
    },
    {
      label: '19 - 35',
      value: '19-35',
    },
    {
      label: '36 - 55',
      value: '36-55',
    },
    {
      label: '56 and above',
      value: '56_above',
    },
  ];
  return <Dropdown options={options} withCheckbox={true} className="w-25" placeholder="Select" />;
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Below 18',
      value: 'below_18',
      subInfo: 'People below 18 years old',
    },
    {
      label: '19 - 35',
      value: '19-35',
      subInfo: 'People 19-35 years old',
    },
    {
      label: '36 - 55',
      value: '36-55',
      subInfo: 'People 36-55 years old',
    },
    {
      label: '56 and above',
      value: '56_above',
      subInfo: 'People above 56 years old',
    },
  ];
  return <Dropdown options={options} withCheckbox={true} className="w-25" placeholder="Select" />;
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Not yet helped',
      value: 'not_yet_helped',
      icon: 'more_horiz',
    },
    {
      label: 'Eligible',
      value: 'eligible',
      icon: 'add',
    },
    {
      label: 'Not Eligible',
      value: 'not_eligible',
      icon: 'horizontal_rule',
    },
    {
      label: 'Got help',
      value: 'got_help',
      icon: 'check',
    },
  ];
  return <Dropdown options={options} optionType="WITH_ICON" className="w-25" placeholder="Select status" />;
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Lawson, Joy',
      value: 'Lawson_Joy',
      subInfo: 'Patient',
    },
    {
      label: 'West, Sarah',
      value: 'West_Sarah',
      subInfo: 'Primary Care Physician',
    },
    {
      label: 'Powell, Lauren',
      value: 'Powell_Lauren',
      subInfo: 'Care Manager',
    },
  ];

  return <Dropdown options={options} optionType="WITH_META" className="w-25" placeholder="Select Recipient" />;
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [];
  for (let i=1; i <= 50; i++) {
    options.push({
      label: `Option ${i}`,
      value: `Option${i}`
    })
  }

  return (
    <Dropdown
      options={options}
      withCheckbox={true}
      withSearch={true}
      className="w-25"
      placeholder="Select"
  />
  );
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [];
  for (let i=1; i <= 100; i++) {
    options.push({
      label: `Option ${i}`,
      value: `Option${i}`
    })
  }

  const getSearchedOptions = (options, searchTerm) => {
    const result = options.filter((option) => option.label.toLowerCase().includes(searchTerm.toLowerCase()));
    return result;
  };

  const fetchOptions = (searchTerm) => {
    const searchedOptions = searchTerm ? getSearchedOptions(options, searchTerm) : options;
    return new Promise(resolve => {
      this.window.setTimeout(() => {
        resolve({
          searchTerm,
          options: searchedOptions,
          count: searchedOptions.length,
        });
      }, 1000);
    });
  };

  return (
    <Dropdown
      fetchOptions={fetchOptions}
      withCheckbox={true}
      className="w-25"
      placeholder="Select"
  />
  );
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Cardiovascular',
      value: 'Cardiovascular',
    },
    {
      label: 'Communication impediments: hearing and vision loss, low literacy',
      value: 'Communication impediments: hearing and vision loss, low literacy',
    },
    {
      label: 'Community resource availability',
      value: 'Community resource availability',
    },
    {
      label: 'Depression and anxiety screenings',
      value: 'Depression and anxiety screenings',
    },
    {
      label: 'Obesity',
      value: 'Obesity',
    },
    {
      label: 'Diabetes',
      value: 'Diabetes',
    },
    {
      label: 'Gastrointestinal system',
      value: 'Gastrointestinal system',
    },
    {
      label: 'Patient has suicidal thoughts',
      value: 'Patient has suicidal thoughts',
    },
    {
      label: 'LTSS needs',
      value: 'LTSS needs',
    },
    {
      label: 'Medication regimen',
      value: 'Medication regimen',
    },
  ];
  return (
    <Dropdown
      options={options}
      withSearch={true}
      className="w-25"
      placeholder="Select problem"
      withCheckbox={true}
      showApplyButton={true}
    />
  );
}
```


#### Dropdown

```jsx
import { Label, Dropdown, HelpText } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Alabama (205)',
      value: 'Alabama (205)',
    },
    {
      label: 'Alabama (251)',
      value: 'Alabama (251)',
    },
    {
      label: 'Alabama (256)',
      value: 'Alabama (256)',
    },
    {
      label: 'Alabama (334)',
      value: 'Alabama (334)',
    },
    {
      label: 'Alabama (938)',
      value: 'Alabama (938)',
    },
    {
      label: 'Arizona (520)',
      value: 'Arizona (520)',
    },
    {
      label: 'California (209)',
      value: 'California (209)',
    },
    {
      label: 'California (408)',
      value: 'California (408)',
    },
    {
      label: 'Colorado (719)',
      value: 'Colorado (719)',
    },
    {
      label: 'Connecticut (860)',
      value: 'Connecticut (860)',
    },
  ];
  return (
    <>
      <Label withInput={true}>Area code</Label>
      <div className="w-25">
        <Dropdown options={options} withSearch={true} placeholder="Select an area code" />
        <HelpText message={'If the number with this code is not available, we will use the next best match'} />
      </div>
    </>
  );
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Alabama',
      value: 'AL',
    },
    {
      label: 'Alaska',
      value: 'AK',
    },
    {
      label: 'Arizona',
      value: 'AZ',
    },
    {
      label: 'Arkansas',
      value: 'AR',
    },
    {
      label: 'California',
      value: 'CO',
    },
    {
      label: 'Connecticut',
      value: 'CT',
    },
    {
      label: 'Delaware',
      value: 'DE',
    },
    {
      label: 'Florida',
      value: 'FL',
    },
    {
      label: 'Georgia',
      value: 'GA',
    },
    {
      label: 'Hawaii',
      value: 'HI',
    },
    {
      label: 'Idaho',
      value: 'ID',
    },
    {
      label: 'Illinois',
      value: 'IL',
    },
    {
      label: 'Indiana',
      value: 'IN',
    },
    {
      label: 'Iowa',
      value: 'IA',
    },
    {
      label: 'Kansas',
      value: 'KS',
    },
    {
      label: 'Kentucky',
      value: 'KY',
    },
    {
      label: 'Louisiana',
      value: 'LA',
    },
    {
      label: 'Maine',
      value: 'ME',
    },
    {
      label: 'Maryland',
      value: 'KY',
    },
    {
      label: 'Massachusetts',
      value: 'MA',
    },
    {
      label: 'Michigan',
      value: 'MI',
    },
    {
      label: 'Minnesota',
      value: 'MN',
    },
    {
      label: 'Mississippi',
      value: 'MS',
    },
    {
      label: 'Missouri',
      value: 'MO',
    },
    {
      label: 'Montana',
      value: 'MT',
    },
    {
      label: 'Nebraska',
      value: 'NE',
    },
    {
      label: 'Nevada',
      value: 'NV',
    },
    {
      label: 'New Hampshire',
      value: 'NT',
    },
    {
      label: 'New Jersey',
      value: 'NJ',
    },
    {
      label: 'New Mexico',
      value: 'NM',
    },
    {
      label: 'New York',
      value: 'NY',
    },
    {
      label: 'North Carolina',
      value: 'NC',
    },
    {
      label: 'North Dakota',
      value: 'ND',
    },
    {
      label: 'Ohio',
      value: 'OH',
    },
    {
      label: 'Oklahoma',
      value: 'OK',
    },
    {
      label: 'Oregon',
      value: 'OR',
    },
    {
      label: 'Pennsylvania',
      value: 'PA',
    },
    {
      label: 'Rhode Island',
      value: 'RI',
    },
    {
      label: 'South Carolina',
      value: 'SC',
    },
    {
      label: 'South Dakota',
      value: 'SD',
    },
    {
      label: 'Tennessee',
      value: 'TN',
    },
    {
      label: 'Texas',
      value: 'TX',
    },
    {
      label: 'Utah',
      value: 'UT',
    },
    {
      label: 'Vermont',
      value: 'VT',
    },
    {
      label: 'Virginia',
      value: 'VA',
    },
    {
      label: 'Washington',
      value: 'WA',
    },
    {
      label: 'West Virginia',
      value: 'WV',
    },
    {
      label: 'Wisconsin',
      value: 'WI',
    },
    {
      label: 'Wyoming',
      value: 'WY',
    },
  ];
  return (
    <Dropdown options={options} icon="location_on" className="w-25" placeholder="Select state" staticLimit={100} />
  );
}
```


#### Dropdown

```jsx
import { Label, Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Male',
      value: 'Male',
      selected: true,
    },
    {
      label: 'Female',
      value: 'Female',
    },
  ];
  return (
    <div className="mb-10 w-25">
      <Label withInput={true}>Gender</Label>
      <Dropdown options={options} />
    </div>
  );
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'All',
      value: 'all',
      selected: true,
    },
    {
      label: 'Draft',
      value: 'draft',
    },
    {
      label: 'In Progress',
      value: 'in_progress',
    },
    {
      label: 'Sent',
      value: 'sent',
    },
    {
      label: 'Scheduled',
      value: 'scheduled',
    },
    {
      label: 'Partially Failed',
      value: 'partially_failed',
    },
    {
      label: 'Completely Failed',
      value: 'completely_failed',
    },
  ];
  return (
    <div>
      <Dropdown options={options} className="w-25" inlineLabel="Status" withCheckbox={true} />
    </div>
  );
}
```


#### Dropdown

```jsx
import { Label, Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'All',
      value: 'all',
      selected: true,
    },
    {
      label: 'Draft',
      value: 'draft',
    },
    {
      label: 'In Progress',
      value: 'in_progress',
    },
    {
      label: 'Sent',
      value: 'sent',
    },
    {
      label: 'Scheduled',
      value: 'scheduled',
    },
    {
      label: 'Partially Failed',
      value: 'partially_failed',
    },
    {
      label: 'Completely Failed',
      value: 'completely_failed',
    },
  ];
  return (
    <div>
      <div className="w-25 mb-9">
        <Label withInput={true}>Status</Label>
        <Dropdown options={options} className="w-100" withCheckbox={true} />
      </div>
    </div>
  );
}
```


#### Dropdown

```jsx
import { Label, Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Hindi',
      value: 'Hindi',
    },
    {
      label: 'English',
      value: 'English',
    },
    {
      label: 'French',
      value: 'French',
    },
  ];
  return (
    <div className="mb-11 w-25">
      <Label withInput={true}>Select Language</Label>
      <Dropdown options={options} />
    </div>
  );
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Financial',
      value: 'financial',
    },
    {
      label: 'Homeless',
      value: 'homeless',
    },
    {
      label: 'Lack of Benefits',
      value: 'lack_of_benefits',
    },
    {
      label: 'Lack of Employment',
      value: 'lack_of_employment',
    },
    {
      label: 'Lack of Understanding',
      value: 'lack_of_understanding',
    },
  ];
  return <Dropdown options={options} withSearch={true} className="w-25" placeholder="Select barriers" />;
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Draft',
      value: 'draft',
    },
    {
      label: 'In Progress',
      value: 'in_progress',
    },
    {
      label: 'Sent',
      value: 'sent',
    },
    {
      label: 'Scheduled',
      value: 'scheduled',
    },
    {
      label: 'Partially Failed',
      value: 'partially_failed',
    },
    {
      label: 'Completely Failed',
      value: 'completely_failed',
    },
  ];
  return <Dropdown options={options} className="w-25" placeholder="Status" />;
}
```


#### Dropdown

```jsx
import { Dropdown } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'All',
      value: 'All',
    },
    {
      label: 'Pending',
      value: 'Pending',
    },
    {
      label: 'Completed',
      value: 'Completed',
    },
  ];
  return (
    <div className="mb-11 w-25">
      <Dropdown options={options} placeholder="All Categories" />
    </div>
  );
}
```


#### Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const storyOptions = [];
  for (let i = 1; i <= 10; i++) {
    storyOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      icon: 'events',
      subInfo: 'subInfo'
    });
  }

  return (
    <div className='d-flex'>
      <div className='mr-12'>
        <Text weight="strong">Towards Right</Text> <br /><br />
        <Dropdown menu={true} options={storyOptions} align='right'/>
      </div>
      <div>
        <Text weight="strong">Towards Left</Text> <br /><br />
        <Dropdown menu={true} options={storyOptions} align='left'/>
      </div>
    </div>
  )
}
```


#### Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const storyOptions = [];
  for (let i = 1; i <= 10; i++) {
    storyOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      icon: 'events',
      subInfo: 'subInfo'
    });
  }

  return (
    <div className='d-flex'>
      <div className='mr-8 w-25'>
        <Text weight="strong">Disabled</Text> <br /><br />
        <Dropdown disabled={true} options={storyOptions} />
      </div>
      <div className='mr-8 w-25'>
        <Text weight="strong">Enabled</Text> <br /><br />
        <Dropdown disabled={false} options={storyOptions} />
      </div>
    </div>
  )
}
```


#### Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const disabledStoryOptions = [];
  for (let i = 1; i <= 10; i++) {
    disabledStoryOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      disabled: i===2
    });
  }

  const onClose = (options) => {
    console.log(options);
  };

  const onChangeHandler = (selectedValues) => {
    console.log(selectedValues);
  };

  return (
    <div className='d-flex'>
      <div className='mr-9 w-25'>
      <Text weight="strong">{'With Checkbox'}</Text><br /><br />
        <Dropdown
          withCheckbox={true}
          withSelectAll={false}
          options={disabledStoryOptions}
          placeholder={'Select'}
          onChange={onChangeHandler}
          onClose={onClose}
        />
      </div>
      <div className="mr-9 w-25">
        <Text weight="strong">{'Without Checkbox'}</Text><br /><br />
        <Dropdown
          options={disabledStoryOptions}
          placeholder={'Select'}
          onChange={onChangeHandler}
          onClose={onClose}
        />
      </div>
    </div>
  )
}
```


#### Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const storyOptions = [];
  for (let i = 1; i <= 10; i++) {
    storyOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      icon: 'events',
      subInfo: 'subInfo'
    });
  }

  return (
    <div className='d-flex'>
      <div className='mr-8 w-25'>
        <Text weight="strong">Default</Text><br /><br />
        <Dropdown options={storyOptions} optionType={'DEFAULT'} loading={true}/>
      </div>
      <div className='mr-8 w-25'>
        <Text weight="strong">Icon</Text><br /><br />
        <Dropdown options={storyOptions} optionType={'WITH_ICON'} loading={true}/>
      </div>
      <div className='mr-8 w-25'>
        <Text weight="strong">SubInfo</Text><br /><br />
        <Dropdown options={storyOptions} optionType={'WITH_META'} loading={true}/>
      </div>
      <div className='mr-8 w-25'>
        <Text weight="strong">Icon with subInfo</Text><br /><br />
        <Dropdown options={storyOptions} optionType={'ICON_WITH_META'} loading={true}/>
      </div>
      <div className='mr-8 w-25'>
        <Text weight="strong">{'Checkboxes'}</Text><br /><br />
        <Dropdown options={storyOptions} withCheckbox={true} loading={true}/>
      </div>
    </div>
  )
}
```


#### Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const storyOptions = [];
  for (let i = 1; i <= 10; i++) {
    storyOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      icon: 'events',
      subInfo: 'subInfo'
    });
  }

  const onClose = (options) => {
    console.log(options);
  };

  const onChangeHandler = (selectedValues) => {
    console.log(selectedValues);
  };

  return (
    <div className='d-flex'>
      <div className='mr-9 w-25'>
        <Text weight="strong">{'With Apply Button'}</Text><br /><br />
        <Dropdown
          maxHeight={180}
          withCheckbox={true}
          showApplyButton={true}
          options={storyOptions}
          placeholder={'Select'}
          onChange={onChangeHandler}
          onClose={onClose}
        />
      </div>
      <div className='mr-9 w-25'>
        <Text weight="strong">{'Without Apply Button'}</Text><br /><br />
        <Dropdown
          withCheckbox={true}
          options={storyOptions}
          placeholder={'Select'}
          onChange={onChangeHandler}
          onClose={onClose}
        />
      </div>
      <div className='mr-9 w-25'>
        <Text weight="strong">{'Without Select All (Options <= 50)'}</Text><br /><br />
        <Dropdown
          withCheckbox={true}
          withSelectAll={false}
          options={storyOptions}
          placeholder={'Select'}
          onChange={onChangeHandler}
          onClose={onClose}
        />
      </div>
    </div>
  )
}
```


#### Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const optionTypes = ['DEFAULT', 'WITH_ICON', 'WITH_META', 'ICON_WITH_META'];

  return (
    <div className="d-flex">
      {optionTypes.map((type, ind) => {
        return (
          <div className="d-flex flex-column mr-9 w-25" key={ind}>
            <Text weight="strong">{labelMapping[type]}</Text>
            <br />
            <Dropdown options={optionsMapping[type].slice(0, 3)} />
          </div>
        );
      })}
      <div className="d-flex flex-column w-25">
        <Text weight="strong">{'Checkboxes'}</Text>
        <br />
        <Dropdown options={storyOptions.slice(0, 3)} withCheckbox={true} />
      </div>
    </div>
  );
}
```


#### Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <div className="mr-9 w-25">
        <Text weight="strong">{'Search'}</Text>
        <br />
        <br />
        <Dropdown withSearch={true} options={storyOptions} />
      </div>
      <div className="mr-9 w-25">
        <Text weight="strong">{'Loading'}</Text>
        <br />
        <br />
        <Dropdown withSearch={true} loading={true} />
      </div>
      <div className="mr-9 w-25">
        <Text weight="strong">{'No Result'}</Text>
        <br />
        <br />
        <Dropdown withSearch={true} noResultMessage={'No result found'} />
      </div>
    </div>
  );
}
```


#### Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const options = [];

  for (let i = 1; i <= 10; i++) {
    options.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      group: 'Group',
    });
  }
  const BooleanValue = [true, false];

  return (
    <div className="d-flex">
      {BooleanValue.map((value, index) => {
        return (
          <div key={index} className="d-flex flex-column align-items-center">
            <Text weight="strong">{value ? ' Multi Select' : 'Single Select'}</Text>
            <br />
            <div className="d-flex">
              <div className="d-flex flex-column align-items-center mr-7">
                <Text weight="strong">{'With Sections'}</Text>
                <br />
                <Dropdown options={options} withCheckbox={value} />
              </div>
              <div className="d-flex flex-column align-items-center mr-7">
                <Text weight="strong">{'Without Sections'}</Text> <br />
                <Dropdown options={storyOptions} withCheckbox={value} />
              </div>
            </div>
            <br />
          </div>
        );
      })}
    </div>
  );
}
```


#### Dropdown

```jsx
import { Text, Dropdown } from '@innovaccer/design-system';

() => {
  const storyOptions = [];
  for (let i = 1; i <= 10; i++) {
    storyOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      icon: 'events',
      subInfo: 'subInfo'
    });
  }

  const disabled = [true, false];

  return (
    <div className='d-flex'>
      <div className='mr-8 w-25'>
        <Text weight="strong">Tiny</Text> <br /><br />
        <Dropdown triggerSize={'tiny'} options={storyOptions} />
      </div>
      <div className='mr-8 w-25'>
        <Text weight="strong">Regular</Text> <br /><br />
        <Dropdown triggerSize={'regular'} options={storyOptions}/>
      </div>
    </div>
  );
}
```


#### Dropdown

```jsx
import { Icon, Text, Dropdown } from '@innovaccer/design-system';

() => {
  const fetchOptions = (searchTerm) => {
    return new Promise((resolve) => {
      this.window.setTimeout(() => {
        resolve({
          searchTerm,
          options: [],
          count: 0,
        });
      }, 1000);
    });
  };
  
    const errorTemplate = (errorType) => {
      console.log(errorType);
      return (
        <div className="my-3 px-7 d-flex vh-25">
          <div className="d-flex flex-column justify-content-center align-items-center">
            <Icon name="error" appearance="alert" />
            <Text className="mb-3" weight="strong">
              Failed to fetch data
            </Text>
            <Text className="text-align-center" weight="medium" size="small" appearance="subtle">
              We couldn't load the data, try reloading.
            </Text>
          </div>
        </div>
      );
    };
  
    return <Dropdown fetchOptions={fetchOptions} className="w-25" placeholder="Select" errorTemplate={errorTemplate} />;
}
```# Dropzone



### Code Examples

#### Components File Uploader Dropzone All

```jsx
import { Button, Dropzone, LinkButton, FileList } from '@innovaccer/design-system';

() => {
  const [files, setFiles] = React.useState([]);

  const getSize = (size) => (
    `${(size / (1024 * 1024)).toFixed(2)} MB`
  );

  const onDelete = (fileItem) => {
    const updatedFiles = files.filter((file) => file.id !== fileItem.id);
    setFiles(updatedFiles);
  };

  const onDropHandler = (event, acceptedFiles, rejectedFiles) => {
    const acceptedFileDetailList = acceptedFiles.map((file, id) => (
      {
        file,
        id: files.length + id,
        fileSize: getSize(file.size),
        networkError: false,
      }
    ));

    const rejectedFilesDetailList = rejectedFiles.map((rejectedFile, id) => {
      const { file, errors } = rejectedFile;
      const errorMessageArray = errors.map((error) => error.message);
      return {
        file,
        id: files.length + id,
        fileSize: getSize(file.size),
        status: 'error',
        errorMessage: errorMessageArray.join(' and '),
        networkError: false,
      };
    });
    const updatedFiles = [...files, ...acceptedFileDetailList, ...rejectedFilesDetailList];
    setFiles(updatedFiles);
  };

  const actionRenderer = (fileItem) => {
    return (
      <React.Fragment>
        {fileItem.networkError && (
          <Button
            aria-label={`Remove ${fileItem.file.name}`}
            appearance="transparent"
            icon="refresh"
            size="regular"
            onClick={() => onDelete(fileItem.id)}
            className={'cursor-pointer'}
          />
        )}
        <Button
          aria-label={`Remove ${fileItem.file.name}`}
          appearance="transparent"
          icon="close"
          size="regular"
          onClick={() => onDelete(fileItem)}
          className={'cursor-pointer'}
        />
      </React.Fragment>
    );
  }

  const handleDownloadClick = () => {
    const link = document.createElement('a');
    link.href = 'https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf';
    link.download = 'Test.pdf';
    link.target = "_blank";
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
  }

  return (
    <React.Fragment>
      <Dropzone
        accept="image/jpeg, image/png"
        formatLabel="Accepted formats: jpeg, png"
        sizeLabel="Maximum size: 25 MB"
        multiple={true}
        onDrop={onDropHandler}
        maxSize={26214400}
        className="mb-5"
        sampleFileLink={<LinkButton onClick={handleDownloadClick}>Download sample file</LinkButton>}
      />
      <FileList
        fileList={files}
        actionRenderer={actionRenderer}
      />
    </React.Fragment>
  );
}
```


#### Components File Uploader Dropzone Variants Disabled

```jsx
import { Dropzone, Text } from '@innovaccer/design-system';

() => {
  const onDrop = (event, acceptedFiles, rejectedFiles) => {
    console.log(acceptedFiles, rejectedFiles);
  };

  return (
    <div className="w-50 d-flex flex-column align-items-center">
      <Dropzone
        onDrop={onDrop}
        disabled={true}
        className="mb-3"
      />
      <Text size="large" weight="strong">Standard</Text>
      <Dropzone
        onDrop={onDrop}
        disabled={true}
        type="compressed"
        className="mt-6 mb-3"
      />
      <Text size="large" weight="strong">Compressed</Text>
      <Dropzone
        onDrop={onDrop}
        disabled={true}
        type="tight"
        className="mt-6 mb-3"
      />
      <Text size="large" weight="strong">Tight</Text>
    </div>
  );
}
```


#### Components File Uploader Dropzone Variants Format

```jsx
import { Dropzone, LinkButton } from '@innovaccer/design-system';

() => {
  const onDrop = (event, acceptedFiles, rejectedFiles) => {
    console.log(acceptedFiles, rejectedFiles);
  };

  const handleDownloadClick = () => {
    const link = document.createElement('a');
    link.href = 'https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf';
    link.download = 'Test.pdf';
    link.target = '_blank';
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
  };

  return (
    <Dropzone
      accept="image/jpeg, image/png"
      formatLabel="Accepted formats: jpeg, png"
      onDrop={onDrop}
      className="mb-3"
      sampleFileLink={<LinkButton onClick={handleDownloadClick}>Download sample file</LinkButton>}
    />
  );
}
```


#### Components File Uploader Dropzone Variants Size

```jsx
import { Dropzone, LinkButton, Text } from '@innovaccer/design-system';

() => {
  const onDrop = (event, acceptedFiles, rejectedFiles) => {
    console.log(acceptedFiles, rejectedFiles);
  };

  const handleDownloadClick = () => {
    const link = document.createElement('a');
    link.href = 'https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf';
    link.download = 'Test.pdf';
    link.target = '_blank';
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
  };

  return (
    <div className="w-50 d-flex flex-column align-items-center">
      <Dropzone
        onDrop={onDrop}
        className="mb-3"
        sampleFileLink={<LinkButton onClick={handleDownloadClick}>Download sample file</LinkButton>}
      />
      <Text size="large" weight="strong">Standard</Text>
      <Dropzone
        onDrop={onDrop}
        type="compressed"
        className="mt-6 mb-3"
        sampleFileLink={<LinkButton onClick={handleDownloadClick}>Download sample file</LinkButton>}
      />
      <Text size="large" weight="strong">Compressed</Text>
      <Dropzone
        onDrop={onDrop}
        type="tight"
        className="mt-6 mb-3"
        sampleFileLink={<LinkButton onClick={handleDownloadClick}>Download sample file</LinkButton>}
      />
      <Text size="large" weight="strong">Tight</Text>
    </div>
  );
}
```# EditableChipInput



### Code Examples

#### Components Inline Editable Fields EditableChipInput All

```jsx
import { EditableChipInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState();

  const onChange = (updatedValue) => {
    setValue(updatedValue);
  };
  const onClick = (item) =>  console.log(item);

  const placeholder ='Add Value';
  const chipOptions = {
    onClick,
    clearButton: true,
    maxWidth: 'var(--spacing-8)',
  };
  const chipInputOptions = {
    chipOptions,
    allowDuplicates:false,
    defaultValue:[],
    autoFocus:true
  };

  const options = {
    placeholder,
    value,
    onChange,
    chipInputOptions
  };
  return (
      <div className="w-25">
        <EditableChipInput
          {...options}
        />
      </div>
  );
}
```


#### Components Inline Editable Fields EditableChipInput Overflow Behavior

```jsx
import { Label, EditableChipInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(["John","Eric","Martin", "Joy"]);

  const onChange = (updatedValue) => {
    setValue(updatedValue);
  };
  const onClick = (item) =>  console.log(item);

  const placeholder ='Add Value';
  const chipOptions = {
    onClick,
    clearButton: true,
    maxWidth: 'var(--spacing-8)',
  };
  const chipInputOptions = {
    chipOptions,
    allowDuplicates:false,
    defaultValue:[],
    autoFocus:true
  };

  const options = {
    placeholder,
    value,
    onChange,
    chipInputOptions
  };
  return (
      <div className="w-25">
        <Label>Members</Label>
        <EditableChipInput
          {...options}
        />
      </div>
  );
}
```


#### Components Inline Editable Fields EditableChipInput Uncontrolled

```jsx
import { EditableChipInput } from '@innovaccer/design-system';

() => {
  const onClick = (item) => console.log(`onClick: ${item}`);
  const chipOptions = {
    onClick,
    clearButton: true,
    maxWidth: 'var(--spacing-8)',
  };
  const chipInputOptions = {
    chipOptions,
    allowDuplicates: false,
    defaultValue: [],
    autoFocus: true,
  };

  const options = {
    chipInputOptions,
    placeholder: 'Add Value',
  };
  return (
    <div className="w-25">
      <EditableChipInput {...options} />
    </div>
  );
}
```# EditableDropdown



### Code Examples

#### Components Inline Editable Fields EditableDropdown All

```jsx
import { Label, EditableDropdown } from '@innovaccer/design-system';

() => {
  const dropdownOptions = [];
  for (let i = 1; i <= 100; i++) {
    dropdownOptions.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      group: i >= 1 && i <= 40 ? 'Group 1' : 'Group 2',
      selected: i === 2
    });
  };

  const getSearchedOptions = (options, searchTerm) => {
    const result = options.filter((option) => option.label.toLowerCase().includes(searchTerm.toLowerCase()));
    return result;
  };

  const fetchOptions = (searchTerm) => {
    const searchedOptions = searchTerm ? getSearchedOptions(dropdownOptions, searchTerm) : dropdownOptions;
    return new Promise(resolve => {
      this.window.setTimeout(() => {
        resolve({
          options: searchedOptions,
          count: searchedOptions.length,
        });
      }, 1000);
    });
  };

  const onChange = (selectedValues) => {
    console.log(selectedValues);
  };

  return (
    <div className="w-25">
      <Label withInput={true} className="ml-5">Editable Dropdown</Label>
      <EditableDropdown
        placeholder="Select Option"
        dropdownOptions={{
          fetchOptions,
          onChange
        }}
      />
    </div>
  );
}
```


#### Components Inline Editable Fields EditableDropdown Custom Render

```jsx
import { StatusHint, Icon, Label, EditableDropdown } from '@innovaccer/design-system';

/*
// style.css
.EditableDropdown-customTrigger {
  border-radius: var(--spacing-m);
}
*/

() => {
  const options = [];
  for (let i = 1; i <= 10; i++) {
    options.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
      group: i >= 1 && i <= 40 ? 'Group 1' : 'Group 2',
      selected: i === 2
    });
  };

  const onChange = (selectedValues) => {
    console.log(selectedValues);
  };

  const customRenderer = (label) => {
    return (
      <StatusHint appearance="warning">{label}</StatusHint>
    );
  };

  const optionRenderer = (props) => {
    const { label } = props.optionData;
    return (
      <StatusHint className="px-5 py-4 cursor-pointer" appearance="warning">{label}</StatusHint>
    );
  };

  const customTrigger = (label) => {
    return (
      <div className="d-flex align-items-center justify-content-between pl-5 pr-4 bg-secondary cursor-pointer w-100 EditableDropdown-customTrigger">
        <StatusHint appearance="warning">{label}</StatusHint>
        <Icon name="keyboard_arrow_down" className="m-4"/>
      </div>
    );
  };

  return (
    <div className="w-25">
      <Label withInput={true} className="ml-5">Editable Dropdown</Label>
      <EditableDropdown
        customTriggerRenderer={customRenderer}
        placeholder="Select Option"
        dropdownOptions={{
          options,
          onChange,
          optionRenderer,
          triggerOptions: { customTrigger },
        }}
      />
    </div>
  );
}
```# EditableInput



### Code Examples

#### Components Inline Editable Fields EditableInput All

```jsx
import { EditableInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState('');

  const onChange = (updatedValue) => {
    setValue(updatedValue);
  };

  const options = {
    placeholder: 'First Name',
    onChange,
    value,
  };

  return (
    <div className="vw-25">
      <EditableInput
        {...options}
      />
    </div>
  );
}
```


#### Components Inline Editable Fields EditableInput Variants Error

```jsx
import { EditableInput } from '@innovaccer/design-system';

/*
// style.css
.EditableInput-wrapper--error {
  width: var(--spacing-9);
}

*/
() => {
  const [value, setValue] = React.useState('');

  const onChange = (value) => {
    setValue(value);
  }

  return (
    <div className='EditableInput-wrapper--error'>
      <EditableInput
        placeholder="First Name"
        value={value}
        onChange={onChange}
        error={true}
        errorMessage={'Error Message'}
      />
    </div>
  );
}
```


#### Components Inline Editable Fields EditableInput Variants Size

```jsx
import { Row, Label, EditableInput, Column } from '@innovaccer/design-system';

() => {
  const [name, setName] = React.useState('');
  const [weight, setWeight] = React.useState('');

  const onChangeName = (value) => {
    setName(value);
  };

  const onChangeWeight = (value) => {
    setWeight(value);
  }

  return (
    <Row>
      <div className="d-flex flex-column vw-25">
        <Label withInput={true} className="ml-5">Regular</Label>
        <EditableInput
          placeholder="First Name"
          value={name}
          onChange={onChangeName}
          className="mr-5"
        />
      </div>
      <Column size={2}>
        <div className="d-flex ml-8 flex-column">
          <Label withInput={true} className="ml-5">Tiny</Label>
          <EditableInput
            placeholder="Add Weight"
            value={weight}
            onChange={onChangeWeight}
            size="tiny"
          />
        </div>
      </Column>
    </Row>
  );
}
```


#### Components Inline Editable Fields EditableInput Variants Uncontrolled

```jsx
import { EditableInput } from '@innovaccer/design-system';

() => {
  return (
    <div className="vw-25">
      <EditableInput placeholder="First Name" />
    </div>
  );
}
```# EmptyState

The empty state indicates the absence of data and helps guide users on expected content and next steps.

### Code Examples

#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import noFilesEmptyFiles from '@innovaccer/mds-images/ui-states/no-files-empty-files.svg';

  return (
    <EmptyState>
      <EmptyState.Image src="https://mds.innovaccer.com/static/media/no-files-empty-files.442ee36a.svg" />
      {/* Replace image path used above with imported image file name
      <EmptyState.Image src={noFilesEmptyFiles} /> */}

      <EmptyState.Title>Title goes here</EmptyState.Title>
      <EmptyState.Description>Description goes here</EmptyState.Description>
      <EmptyState.Actions>
        <Button className="mr-4">Secondary action</Button>
        <Button appearance="primary">Primary action</Button>
      </EmptyState.Actions>
    </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import noFilesEmptyFiles from '@innovaccer/mds-images/ui-states/no-files-empty-files.svg';

  return (
      <EmptyState size="compressed">
        <EmptyState.Image src={"static/media/no-files-empty-files.442ee36a.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={noFilesEmptyFiles}></EmptyState.Image> */}

        <EmptyState.Title>Title goes here</EmptyState.Title>
        <EmptyState.Description>
          Description goes here
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button className="mr-4">Secondary action</Button>
          <Button appearance="primary">Primary action</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import noFilesEmptyFiles from '@innovaccer/mds-images/ui-states/no-files-empty-files.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/no-files-empty-files.442ee36a.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={noFilesEmptyFiles}></EmptyState.Image> */}

        <EmptyState.Title>Title goes here</EmptyState.Title>
        <EmptyState.Description>
          Description goes here
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button className="mr-4">Secondary action</Button>
          <Button appearance="primary">Primary action</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import noFilesEmptyFiles from '@innovaccer/mds-images/ui-states/no-files-empty-files.svg';

  return (
      <EmptyState size="tight">
        <EmptyState.Image src={"static/media/no-files-empty-files.442ee36a.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={noFilesEmptyFiles}></EmptyState.Image> */}

        <EmptyState.Title>Title goes here</EmptyState.Title>
        <EmptyState.Description>
          Description goes here
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button size="tiny" className="mr-4">
            Secondary action
          </Button>
          <Button size="tiny" appearance="primary">
            Primary action
          </Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import noFilesEmptyFiles from '@innovaccer/mds-images/ui-states/no-files-empty-files.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/no-files-empty-files.442ee36a.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={noFilesEmptyFiles}></EmptyState.Image> */}

        <EmptyState.Title>There are no referrals yet</EmptyState.Title>
        <EmptyState.Description>When you create a new referral, you will see it here.</EmptyState.Description>
        <EmptyState.Actions>
          <Button className="mr-4">Secondary action</Button>
          <Button appearance="primary">Primary action</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import noContent from '@innovaccer/mds-images/ui-states/404-nothing-here-3.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/404-nothing-here-3.2871b1b3.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={noContent}></EmptyState.Image> */}

        <EmptyState.Title>Failed to load data</EmptyState.Title>
        <EmptyState.Description>
          We are unable to fetch the data. Try again. If the issue persists, contact Innovaccer support.
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button icon="refresh">Try again</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import connectionLost from '@innovaccer/mds-images/ui-states/connection-lost.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/connection-lost.3faf24fb.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={connectionLost}></EmptyState.Image> */}

        <EmptyState.Title>You are offline</EmptyState.Title>
        <EmptyState.Description>
          Looks like you are not connected to the internet. Check your connection and try again.
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button icon="refresh">Try again</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import lockedState from '@innovaccer/mds-images/ui-states/locked.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/locked.49062ad1.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={lockedState}></EmptyState.Image> */}

        <EmptyState.Title>Access denied</EmptyState.Title>
        <EmptyState.Description>
          You don’t have the access to this page. Contact your admin for more information.
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button>Go back</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import fileNotFound from '@innovaccer/mds-images/ui-states/file-not-found.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/file-not-found.c2ac5177.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={fileNotFound}></EmptyState.Image> */}

        <EmptyState.Title>No results match your criteria</EmptyState.Title>
        <EmptyState.Description>Try adjusting your filters to find what you are looking for.</EmptyState.Description>
        <EmptyState.Actions>
          <Button>Clear filters</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import searchState from '@innovaccer/mds-images/ui-states/search-1.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/search-1.bd60817f.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={searchState}></EmptyState.Image> */}

        <EmptyState.Title>No results found for your search</EmptyState.Title>
        <EmptyState.Description>Try adjusting your search to find what you are looking for.</EmptyState.Description>
        <EmptyState.Actions>
          <Button>Clear search</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import fileBroken from '@innovaccer/mds-images/ui-states/file-broken-or-not-found.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/file-broken-or-not-found.4b77cf60.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={fileBroken}></EmptyState.Image> */}

        <EmptyState.Title>Page does not exist</EmptyState.Title>
        <EmptyState.Description>
          You seem to have followed a dead link. Check the URL or use the go home button given below.
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button>Go home</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import previewContent from '@innovaccer/mds-images/ui-states/content-unavailable.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/content-unavailable.d6622368.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={previewContent}></EmptyState.Image> */}

        <EmptyState.Title>Preview for this file is not available</EmptyState.Title>
        <EmptyState.Description>
          The file size is too big or not supported. You can download the file to view it on your computer.
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button icon="download">Download</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import historyTime from '@innovaccer/mds-images/ui-states/history-time.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/history-time.6e4bb1e4.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={historyTime}></EmptyState.Image> */}

        <EmptyState.Title>This is taking unexpectedly long</EmptyState.Title>
        <EmptyState.Description>
          Failed to complete the request due to slow api response, or server overload. You can try again later.
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button icon="refresh">Try again</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```


#### EmptyState

```jsx
import { EmptyState, Button } from '@innovaccer/design-system';

() => {
  // import errorState from '@innovaccer/mds-images/ui-states/error.svg';

  return (
      <EmptyState>
        <EmptyState.Image src={"static/media/error.59aaebe8.svg"}></EmptyState.Image>
        {/* Replace image path used above with imported image file name
        <EmptyState.Image src={errorState}></EmptyState.Image> */}

        <EmptyState.Title>Uh-oh, our server is taking a nap!</EmptyState.Title>
        <EmptyState.Description>
          The server is unavailable at the moment due to maintenance downtime or capacity problems. You can try again
          later.
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button>Go back</Button>
        </EmptyState.Actions>
      </EmptyState>
  );
}
```# FileList



### Code Examples

#### Components File Uploader FileList All

```jsx
import { FileList, Button } from '@innovaccer/design-system';

() => {
  const fileList = [
    {
      file:{
        name: 'Audio File.mp3',
        size: '3 MB',
        type: 'audio',
      },
      status: 'uploading',
      progress: 45,
      id: 1,
    },
    {
      file:{
        name: 'Video File.mp4',
        size: '3 MB',
        type: 'video',
      },
      status: 'completed',
      id: 2,
    },
    {
      file:{
        name: 'Image file name can be some times very long in size so it will get truncated File.jpeg',
        size: '3 MB',
        type: 'image',
      },
      status: 'error',
      errorMessage: 'Network failure',
      id: 3,
    },
    {
      file:{
        name: 'Document File.pdf',
        size: '3 MB',
        type: 'application',
      },
      status: 'completed',
      id: 4,
    },
    {
      file:{
        name: 'Other File',
        size: '3 MB',
        type: 'others',
      },
      status: 'completed',
      id: 5,
    }
  ];

  const onClick = (file) => {
    console.log(`Clicked: ${file}`);
  };

  return (
    <div className="pt-6 w-50">
      <FileList
        onClick={onClick}
        fileList={fileList}
        actionRenderer={fileItem => {
          if (fileItem.id === 3) {
            return(
              <>
              <Button
                appearance="transparent"
                icon="refresh"
                size="regular"
                onClick={() => onClick(fileItem)}
                className={'cursor-pointer'}
              />
              <Button
                appearance="transparent"
                icon="close"
                size="regular"
                onClick={() => onClick(fileItem)}
                className={'cursor-pointer ml-2'}
              />
            </>
            );
          }
          return (
            <Button
              appearance="transparent"
              icon="close"
              size="regular"
              onClick={() => {}}
              className={'cursor-pointer'}
            />
          );
        }
        }
      />
    </div>
  );
}
```# FileUploader

File uploader is used to upload single or multiple files.

### Code Examples

#### FileUploader

```jsx
import {  } from '@innovaccer/design-system';

() => <></>
```# FullscreenModal



### Code Examples

#### FullscreenModal

```jsx
import { Button, FullscreenModal, Heading, Paragraph } from '@innovaccer/design-system';


() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const openModal = () => {
    setOpen(true);
  };


  return (
    <div>
      <Button className="m-8" appearance="primary" onClick={openModal}>
        Open Full screen modal
      </Button>

      <FullscreenModal
        open={open}
        onClose={onClose}
        headerOptions={{
          heading: 'Heading',
          subHeading: 'Subheading'
        }}
        footerOptions={{
          actions: [
            {
              children: 'Cancel',
              appearance: 'basic',
              onClick: ev => console.log('Basic button click', ev)
            },
            {
              children: 'Done',
              appearance: 'primary',
              className: 'ml-4',
              onClick: ev => console.log('Primary button click', ev)
            }
          ]
        }}
      >
        <div className="pb-6">
          <Heading className="pb-3" size="s">
           Description Title
          </Heading>
          <Paragraph>Adding a subheading clearly indicates the hierarchy of the information.</Paragraph>
        </div>
        <div className="pt-6">
          <Paragraph>
            Card Sections include supporting text like an article summary or a healthcare service description.
          </Paragraph>
        </div>
      </FullscreenModal>
    </div>
  );
}
```


#### FullscreenModal

```jsx
import { Button, FullscreenModal, Heading, Text, Paragraph } from '@innovaccer/design-system';


() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const openModal = () => {
    setOpen(true);
  };


  return (
    <div>
      <Button className="m-8" appearance="primary" onClick={openModal}>
        Open Full screen modal
      </Button>

      <FullscreenModal
        open={open}
        dimension="medium"
        onClose={onClose}
        header={(
          <div className="ml-7">
            <Heading>Custom Heading component</Heading>
            <Text appearance="subtle">This is subheading</Text>
          </div>
        )}
        footer={(
          <>
            <Button appearance="basic" onClick={ev => console.log('Basic button click', ev)}>
              Cancel
            </Button>
            <Button appearance="primary" className="ml-4" onClick={ev => console.log('Primary button click', ev)}>
              Done
            </Button>
          </>
        )}
      >
        <div className="pb-6">
          <Heading className="pb-3" size="s">
            Description Title
          </Heading>
          <Paragraph>Adding a subheading clearly indicates the hierarchy of the information.</Paragraph>
        </div>
        <div className="pt-6">
          <Paragraph>
            Card Sections include supporting text like an article summary or a healthcare service description.
          </Paragraph>
        </div>
      </FullscreenModal>
    </div>
  );
}
```


#### FullscreenModal

```jsx
import { Button, FullscreenModal, Heading, Paragraph, Text } from '@innovaccer/design-system';


() => {
  const [open, setOpen] = React.useState(false);
  const [openSecondOverlay, setOpenSecondOverlay] = React.useState(false);


  const onClose = () => {
    setOpen(!open);
  };

  const openModal = () => {
    setOpen(true);
  };

  const onCloseSecondOverlay = () => {
    setOpenSecondOverlay(!openSecondOverlay);
  };

  const openSecondModal = () => {
    setOpenSecondOverlay(true);
  };


  return (
    <div>

      <Button className="m-8" appearance="primary" onClick={openModal}>
        Open Full screen modal
      </Button>

      <FullscreenModal
        open={open}
        closeOnEscape={true}
        onClose={onClose}
        headerOptions={{
          heading: 'Heading',
          subHeading: 'Subheading'
        }}
        footerOptions={{
          actions: [
            {
              children: 'Cancel',
              appearance: 'basic',
              onClick: ev => console.log('Basic button click', ev)
            },
            {
              children: 'Open',
              appearance: 'primary',
              className: 'ml-4',
              onClick: ev => openSecondModal()
            }
          ]
        }}
      >
        <div className="pb-6">
          <Heading className="pb-3" size="s">
            Description Title
          </Heading>
          <Paragraph>Adding a subheading clearly indicates the hierarchy of the information.</Paragraph>
        </div>
        <div className="pt-6">
          <Paragraph>
            Card sections include supporting text like an article summary or a healthcare service description.
          </Paragraph>
        </div>
      </FullscreenModal>

      <FullscreenModal
        closeOnEscape={true}
        open={openSecondOverlay}
        onClose={onCloseSecondOverlay}
        headerOptions={{
          heading: 'Second modal heading',
          subHeading: 'Second modal subheading'
        }}
        footerOptions={{
          actions: [
            {
              children: 'Cancel',
              appearance: 'basic',
              onClick: ev => console.log('Basic button click', ev)
            }
          ]
        }}
      >
        <Heading size="s">Second description title</Heading>
        <Text>Second fullscreen modal body</Text>
      </FullscreenModal>
    </div>
  );
}
```


#### FullscreenModal

```jsx
import { Button, FullscreenModal, Text, Chip } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const data = [{ question:'Do you experience any of the following in your current place of residence? [Select all that apply]', options:['Deteriorating appearance', 'Inoperable plumbing', 'Inadequate wining', 'Leaking roofs', 'Crumbling foundations', 'Unsafe steps', 'in poor condition', 'None of the above'] },
    { question:'In last 12 months, were you worried that your food would run out before you got money to buy more?',
      options:['Yes', 'No'] },
    { question:'Moving or speaking so slowly that other people could have noticed? Or the opposite - being so fidgety or restless that you have been moving around a lot more than usual', options:['Not at all', 'Several Days', 'More than half the days', 'Nearly every day'] },
    { question:'Feeling tired or having little energy?', options:['Yes', 'No'] },
    { question:'Moving or speaking so slowly that other people could have noticed? Or the opposite - being so fidgety or restless that you have been moving around a lot more than usual', options:['Not at all', 'Several Days', 'More than half the days', 'Nearly every day'] },
    { question:'Moving or speaking so slowly that other people could have noticed? Or the opposite - being so fidgety or restless that you have been moving around a lot more than usual', options:['Not at all', 'Several Days', 'More than half the days', 'Nearly every day'] },
    { question:'Moving or speaking so slowly that other people could have noticed? Or the opposite - being so fidgety or restless that you have been moving around a lot more than usual', options:['Not at all', 'Several Days', 'More than half the days', 'Nearly every day'] },
  ];

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Full screen modal</Button>
      <FullscreenModal
        open={open}
        dimension="large"
        onClose={onClose}
        headerOptions={{
          heading: 'Survey',
        }}
        footer={(
          <>
            <Button  onClick={console.log('Cancel button click')}>Cancel</Button>
            <Button appearance="primary" className="ml-4" onClick={console.log('Submit button click')}>Submit</Button>
          </>
        )}
      >
      <div className="mt-5">
        <Text weight="strong">All questions must be answered, unless marked</Text><br/>
        {
          data.map((object, index) => {
            return(
              <div key={index} className="mt-5 d-flex">
                <div >
                  <Text size="regular" className="mr-4">
                  {`${index + 1}.`}
                  </Text>
                </div>
                <div className="d-inline-block ml-2">
                  <Text size="regular">
                    {object.question}
                  </Text>
                  <div className="mb-5 mt-3">
                    {
                      object.options.map((option, ind) => {
                        return <Chip key={ind} type="selection" label={option} className="mr-4 mt-4" />;
                      })
                    }
                  </div>
                </div>
              </div>
            );
          })
        }
      </div>
      </FullscreenModal>
    </div>
  );
}
```


#### FullscreenModal

```jsx
import { Button, FullscreenModal, Text, Input, Label, Card, List } from '@innovaccer/design-system';


() => {
  const [open, setOpen] = React.useState(false);
  const [page, setPage] = React.useState(0);

  const onClose = () => {
    setOpen(!open);
  };

  const openModal = () => {
    setOpen(true);
  };

  const headerOptions = () => {
    if (page === 0) {
      return(
      {
        heading:'New Care Plan',
      }
      );
    }
    return(
    {
      heading: 'Name the care plan',
      backButton: true,
      backButtonCallback: () => setPage(0)
    }
    );
  };

  const data = [{ name:'Cultural and language barriers', icon: 'close' }, { name:'Patient does not show emotion', icon: 'close' }];

  const schema = [
    {
      name: 'name',
      displayName: 'name',
      width: '80%',
    },
    {
      name: 'icon',
      displayName: 'icon',
      width: '20%',
      minWidth:'10',
      cellType:'ICON',
      align:'right'
    },
  ];

  return (
    <div>
      <Button appearance="primary" onClick={openModal}>
        Open Full screen modal
      </Button>

      <FullscreenModal
        open={open}
        dimension="medium"
        onClose={onClose}
        headerOptions={headerOptions()}
        footer={(
          <>
            {page === 0 && (
              <>
                <Button>
                  Cancel
                </Button>
                <Button appearance="primary" onClick={() => setPage(1)} className="ml-4">
                  Continue
                </Button>
              </>
            )}
            {page === 1 && (
            <>
                <Button>
                  Cancel
                </Button>
                <Button appearance="primary" className="ml-4">
                  Submit
                </Button>
              </>
            )}
          </>
        )}

      >
        {page === 0 && (
          <div>
            <Text weight="strong" size="regular">Identify patient needs</Text><br/>
            <Text  size="small">Identify the patient needs to create a care plan for the patient</Text>
            <Input placeholder="Add patient needs" size="regular" className="my-5"/>
            <Label withInput={true}>2 selected</Label>
            <Card className="w-100" shadow="none">
              <List
                data={data}
                schema={schema}
                size="tight"
              />
            </Card>          
          </div>
        )}
        {page === 1 && (
          <div>
            <Text size="regular">Give a meaningful and easy to understand name to the care plan.</Text><br/>
            <Label required={true} className="mt-5">Name</Label>
            <Input placeholder="Name" size="regular" className="mt-2"/>
          </div>
        )}
      </FullscreenModal>
    </div>
  );
}
```


#### FullscreenModal

```jsx
import { Button, FullscreenModal, Label, Radio, Input, Card, Icon, Text } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(!open);
  };

  const data = [{ iconName: 'message', textMessage: 'Text Message' }, { iconName: 'chat_bubble', textMessage: 'Portal Message' }, { iconName: 'email', textMessage: 'E-mail' }, { iconName: 'markunread_mailbox', textMessage: 'Letter' }, { iconName: 'mic', textMessage: 'Voice Recording' }];

  const cardClassName = (index) => {
    const classname = 'd-flex flex-column align-items-center justify-content-center w-25 py-4'
    return classname.concat((index !== data.length-1) && " mr-4")
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Full screen modal</Button>
      <FullscreenModal
        open={open}
        dimension="large"
        onClose={onClose}
        headerOptions={{
          heading: 'New outreach',
        }}
        footer={(
          <>
            <Button onClick={console.log('Cancel button click')}>Cancel</Button>
            <Button appearance="primary" className="ml-4" onClick={console.log('Next button click')}>Create</Button>
          </>
        )}
      >
        <Label withInput={true}>Type</Label>
        <div className="d-flex">
          <Radio
            defaultChecked={true}
            label="Message outreach"
            name="Outreach"
            size="regular"
            value="Message outreach"
          />
          <Radio label="Survey outreach" name="Outreach" size="regular" value="Survey outreach" className="ml-8" />
        </div>
        <Label withInput={true} className="mt-6">Name</Label>
        <Input placeholder="e.g. Annual Welness Visit outreach, etc." className="mb-5 w-50" />
        <Label withInput={true}>Medium</Label>
        <div className="d-flex">
          {
            data.map((obj, index) => {
              return(
                <Card key={index} shadow="none" 
                className={cardClassName(index)}
                >
                  <Icon name={obj.iconName} size={25}/>
                  <Text className="pt-5" size="small" weight="strong">
                    {obj.textMessage}
                  </Text>
                </Card>
              );
            })
          }
        </div>
      </FullscreenModal>
    </div>
  );
}
```


#### FullscreenModal

```jsx
import { Button, FullscreenModal, Label, Input, Textarea } from '@innovaccer/design-system';

() => {
    const [open, setOpen] = React.useState(false);

    const onClose = () => {
      setOpen(!open);
    };

    return (
      <div>
        <Button appearance="primary" onClick={() => setOpen(true)}>Open Full screen modal</Button>
        <FullscreenModal
          open={open}
          dimension="medium"
          onClose={onClose}
          headerOptions={{
            heading: 'New group',
          }}
          footer={(
            <>
              <Button  onClick={console.log('Cancel button click')}>Cancel</Button>
              <Button appearance="primary" className="ml-4" onClick={console.log('Next button click')}>Create</Button>
            </>
          )}
        >
          <Label withInput={true} required={true}>Name</Label>
          <Input placeholder="Admin" className="mb-5"/>
          <Label withInput={true}>Description</Label>
          <Textarea placeholder="Write a description"/>
        </FullscreenModal>
      </div>
    );
}
```# Grid



### Code Examples

#### Components Grid All

```jsx
import { Card, Grid } from '@innovaccer/design-system';

() => {
  const applyLoaderSchema = true;

  const loading = false;

  const error = false;

  const applySchema = true;

  const applyData = true;

  const totalRecords = data.length;

  const type = 'resource';

  const size = 'comfortable';

  const draggable = true;

  const nestedRows = false;

  const withCheckbox = false;

  const showMenu = true;

  const withPagination = false;

  const page = 1;

  const pageSize = 12;

  const headCellTooltip = false;

  const separator = false;

  return (
    <div className="Grid-outerWrapper">
      <Card className="h-100 overflow-hidden">
        <Grid
          schema={applySchema ? schema : undefined}
          data={applyData ? data : undefined}
          loading={loading}
          error={error}
          errorTemplate={errorTemplate}
          totalRecords={totalRecords}
          withCheckbox={withCheckbox}
          showMenu={showMenu}
          type={type}
          size={size}
          headCellTooltip={headCellTooltip}
          separator={separator}
          draggable={draggable}
          nestedRows={nestedRows}
          nestedRowRenderer={nestedRowRenderer}
          withPagination={withPagination}
          page={page}
          pageSize={pageSize}
          loaderSchema={applyLoaderSchema ? loaderSchema : undefined}
          onRowClick={(rowData, rowIndex) =>
            action(`on-row-click:- rowIndex: ${rowIndex} data: ${JSON.stringify(rowData)}`)()
          }
          onSelect={(rowIndex, selected) => action(`on-select:- rowIndex: ${rowIndex} selected: ${selected}`)()}
          onSelectAll={(selected, selectedAll) => {
            action(`on-select:- selected: ${selected} selectedAll: ${selectedAll}`)();
          }}
          sortingList={[{ name: 'name', type: 'desc' }]}
          filterList={{
            name: ['h-r', 's-z'],
          }}
        />
      </Card>
    </div>
  );
}
```


#### Grid In Modal

```jsx
import { Button, Modal, Grid, Text } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const backdropClose = false;
  const onClose = () => {
    setOpen(!open);
  };
  const gridData = [
    {
      fullname: 'Wadsworth Seden',
      gender: 'Male',
    },
    {
      fullname: 'Jakie Hapke',
      gender: 'Male',
    },
    {
      fullname: 'Louella Veneur',
      gender: 'Female',
    },
  ];
  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Modal
      </Button>
      <Modal
        open={open}
        dimension="large"
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Patients',
        }}
        footer={
          <React.Fragment>
            <Button>Cancel</Button>
            <Button className="ml-4">Next</Button>
          </React.Fragment>
        }
        seperator={true}
      >
        <Grid
          data-test="modal-in-grid"
          totalRecords={5}
          pageSize={5}
          schema={[
            {
              name: 'fullName',
              displayName: 'Name',
              width: '50%',
              cellRenderer: ({ data }) => {
                return (
                  <div className="w-100">
                    <Text className="d-block">{data.fullname}</Text>
                    <Text className="d-block" size="small" appearance="subtle">
                      {data.fullname}
                    </Text>
                  </div>
                );
              },
            },
            {
              name: 'gender',
              displayName: 'Gender',
              width: '50%',
              cellRenderer: ({ data }) => {
                return (
                  <div className="w-100">
                    <Text className="d-block">{data.gender}</Text>
                    <Text className="d-block" size="small" appearance="subtle">
                      {data.gender}
                    </Text>
                  </div>
                );
              },
            },
          ]}
          data={gridData}
          showHead={true}
          showMenu={false}
          loading={false}
        />
      </Modal>
    </div>
  );
}
```


#### Components Grid Variants Grid Loading State

```jsx
import { Grid } from '@innovaccer/design-system';

() => {
  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '50%'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: '50%'
    }
  ];

  return (
    <Grid
      totalRecords={10}
      pageSize={5}
      schema={schema}
      loading={true}
    />
  );
}

```# GridCell



### Code Examples

#### Components Grid Grid Cell

```jsx
import { GridCell } from '@innovaccer/design-system';

() => {
  const schema = {
    name: 'name',
    displayName: 'Name',
  };

  const size = 'comfortable';

  const width = 250;

  const cellType = 'STATUS_HINT';

  const align = 'left';

  const tooltip = true;

  const loading = false;

  return (
    <div className="Grid-cell Grid-cell--body border w-25">
      <div className="Grid-cellContent">
        <GridCell
          size={size}
          rowIndex={1}
          colIndex={1}
          loading={loading}
          data={{
            name: {
              title: 'Schreiber Brynn',
              metaList: ['Meta Item 1', 'Meta Item 2'],
              icon: 'events',
            },
          }}
          schema={{
            ...schema,
            width,
            cellType,
            align,
            tooltip,
          }}
        />
      </div>
    </div>
  );
}
```# Heading



### Code Examples

#### Heading

```jsx
import { Heading } from '@innovaccer/design-system';

() => {
  return <Heading>Heading component have different variants, look for options in knobs tab.</Heading>;
}
```


#### Heading

```jsx
import { Heading, Text } from '@innovaccer/design-system';

() => {
  const appearances = ['default', 'subtle', 'disabled', 'white'];
  return (
    <div className="d-flex">
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="d-flex flex-column mr-7">
            <Heading key={ind} className={appear === 'white' ? 'bg-dark' : 'bg-transparent'} appearance={appear}>
              Heading
            </Heading>
            <br />
            <Text weight="strong">{appear.charAt(0).toUpperCase() + appear.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### Heading

```jsx
import { Heading } from '@innovaccer/design-system';

() => {
  const colorList = [
    [
      'primary',
      'primary-dark',
      'primary-darker',
      'primary-light',
      'primary-lighter',
      'primary-lightest',
      'primary-shadow',
    ],
    [
      'success',
      'success-dark',
      'success-darker',
      'success-light',
      'success-lighter',
      'success-lightest',
      'success-shadow',
    ],
    ['alert', 'alert-dark', 'alert-darker', 'alert-light', 'alert-lighter', 'alert-lightest', 'alert-shadow'],
    [
      'warning',
      'warning-dark',
      'warning-darker',
      'warning-light',
      'warning-lighter',
      'warning-lightest',
      'warning-shadow',
    ],
    [
      'accent1',
      'accent1-dark',
      'accent1-darker',
      'accent1-light',
      'accent1-lighter',
      'accent1-lightest',
      'accent1-shadow',
    ],
    [
      'accent2',
      'accent2-dark',
      'accent2-darker',
      'accent2-light',
      'accent2-lighter',
      'accent2-lightest',
      'accent2-shadow',
    ],
    [
      'accent3',
      'accent3-dark',
      'accent3-darker',
      'accent3-light',
      'accent3-lighter',
      'accent3-lightest',
      'accent3-shadow',
    ],
    [
      'accent4',
      'accent4-dark',
      'accent4-darker',
      'accent4-light',
      'accent4-lighter',
      'accent4-lightest',
      'accent4-shadow',
    ],
    ['secondary', 'secondary-dark', 'secondary-light', 'secondary-lighter', 'secondary-lightest', 'secondary-shadow'],

    ['white', 'inverse', 'inverse-light', 'inverse-lighter', 'inverse-lightest', 'inverse-shadow'],
  ];

  return (
    <div>
      {colorList.map((colors, key) => {
        return (
          <div key={key} className="d-flex justify-content-between w-100 py-4">
            {colors.map((color, ind) => {
              return (
                <Heading key={ind} color={color} size="s" className={color === 'white' ? 'bg-dark' : ''}>
                  {color}
                </Heading>
              );
            })}
          </div>
        );
      })}
    </div>
  );
}
```


#### Heading

```jsx
import { Heading, Text } from '@innovaccer/design-system';

() => {
  const sizes = ['s', 'm', 'l', 'xl', 'xxl'];

  return (
    /*
  // style.css
    .bottom-0 {
      bottom: 0
    }
   */
    <div className="d-flex align-items-center position-relative">
      {sizes.map((HeadingSize, ind) => {
        return (
          <div key={ind} className="mr-7 mb-5">
            <Heading size={HeadingSize}>Heading</Heading>
            <br />
            <Text weight="strong" className="bottom-0 position-absolute">
              {HeadingSize}
            </Text>
          </div>
        );
      })}
    </div>
  );
}
```# HelpText

Help text provides a brief description accompanying a component.

### Code Examples

#### HelpText

```jsx
import { Label, Select, HelpText } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Alabama (205)',
      value: 'Alabama (205)',
    },
    {
      label: 'Alabama (251)',
      value: 'Alabama (251)',
    },
    {
      label: 'Alabama (256)',
      value: 'Alabama (256)',
    },
    {
      label: 'Alabama (334)',
      value: 'Alabama (334)',
    },
    {
      label: 'Alabama (938)',
      value: 'Alabama (938)',
    },
    {
      label: 'Arizona (520)',
      value: 'Arizona (520)',
    },
    {
      label: 'California (209)',
      value: 'California (209)',
    },
    {
      label: 'California (408)',
      value: 'California (408)',
    },
    {
      label: 'Colorado (719)',
      value: 'Colorado (719)',
    },
    {
      label: 'Connecticut (860)',
      value: 'Connecticut (860)',
    },
  ];

  return (
    <>
      <Label withInput={true}>Area code</Label>
      <div className="w-25">
        <Select
          triggerOptions={{
            placeholder: 'Select an area code',
          }}
        >
          <Select.List>
            {options.map((item, key) => {
              return (
                <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                  {item.label}
                </Select.Option>
              );
            })}
          </Select.List>
        </Select>
        <HelpText message={'If the number with this code is not available, we will use the next best match'} />
      </div>
    </>
  );
}
```


#### Components HelpText With Error

```jsx
import { Label, Input, HelpText } from '@innovaccer/design-system';

() => {
  return (
    <div className="w-25">
      <Label required={true} withInput={true}>
        Password
      </Label>
      <Input error={true} name="input" required={true} type="password" />
      <HelpText error={true} message="Pick a strong, unique password" />
    </div>
  );
}
```# HorizontalNav



### Code Examples

#### Components HorizontalNav All

```jsx
import { HorizontalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'menu_1',
      label: 'Menu 1',
      count: 20
    },
    {
      name: 'menu_2',
      label: 'Menu 2',
      count: 10
    },
    {
      name: 'menu_3',
      label: 'Menu 3',
      disabled: true,
      count: 5,
    }
  ];

  const [active, setActive] = React.useState({
    name: 'menu_1'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return (
    <div className="bg-secondary-lightest py-6">
      <HorizontalNav
        className="w-100 justify-content-center"
        menus={data}
        active={active}
        onClick={onClickHandler}
      />
  </div>
  );
}
```


#### Horizontal Nav inside a Standard Modal

```jsx
import { HorizontalNav, Heading, Button, Modal, Label, Select } from '@innovaccer/design-system';

() => {
  const options = [];
  for (let i = 1; i <= 10; i++) {
    options.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
    });
  }

  const data = [
    {
      name: 'medicine',
      label: 'Medicine',
    },
    {
      name: 'period',
      label: 'Period',
    },
    {
      name: 'alias',
      label: 'Alias',
    },
    {
      name: 'priority',
      label: 'Priority',
    },
  ];

  const [open, setOpen] = React.useState(false);
  const [active, setActive] = React.useState({
    name: 'medicine'
  });

  const onClose = () => {
    setOpen(!open);
  };

  const onClickHandler = (menu) => {
    setActive(menu);
  };

  const subHeading = (
    <HorizontalNav
      menus={data}
      active={active}
      onClick={onClickHandler}
      className="ml-5 mt-4"
    />
  );

  const header = (
    <div>
      <Heading className="ml-7 mb-3">Medication</Heading>
      {subHeading}
    </div>
  );

  return (
    <div>
      <Button appearance="primary" className="mt-3" onClick={() => { setOpen(true) }}>Open Modal</Button>
      <Modal
        open={open}
        dimension="large"
        onClose={onClose}
        header={header}
        footer={(
          <>
            <Button appearance="basic">Discard</Button>
            <Button appearance="primary" className="ml-4">Create</Button>
          </>
        )}
        
      >
        <div className="py-5 w-50">
          <Label withInput={true} required={true}>Type</Label>
          <Select triggerOptions={{ withClearButton: false }} width="100%">
            <Select.List>
              {options.map((item, key) => {
                return (
                  <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                    {item.label}
                  </Select.Option>
                );
              })}
            </Select.List>
          </Select>
          <Label withInput={true} className="mt-6">Active Date</Label>
          <Select triggerOptions={{ withClearButton: false }} width="100%">
            <Select.List>
              {options.map((item, key) => {
                return (
                  <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                    {item.label}
                  </Select.Option>
                );
              })}
            </Select.List>
          </Select>
          <Label withInput={true} className="mt-6" required={true}>Diagnosis Diseases</Label>
            <Select triggerOptions={{ withClearButton: false }} width="100%">
            <Select.List>
              {options.map((item, key) => {
                return (
                  <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                    {item.label}
                  </Select.Option>
                );
              })}
            </Select.List>
          </Select>
        </div>
      </Modal>
    </div>
  );
}
```


#### Components HorizontalNav Variants Default Horizontal Nav

```jsx
import { HorizontalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'engagements',
      label: 'Engagements',
    },
    {
      name: 'no_linked_activities',
      label: 'No Linked Activities',
    },
  ];

  const [active, setActive] = React.useState({
    name: 'engagements'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return (
    <div className="d-flex align-items-center py-6 bg-secondary-lightest">
      <HorizontalNav
        className="w-100 justify-content-center"
        menus={data}
        active={active}
        onClick={onClickHandler}
      />
    </div>
  );
}
```


#### Components HorizontalNav Variants With Count

```jsx
import { HorizontalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'to-dos',
      label: 'To-dos',
      count: 15
    },
    {
      name: 'activity_received',
      label: 'Activity received',
      count: 7
    },
    {
      name: 'activity_sent',
      label: 'Activity sent',
      count: 9
    },
  ];

  const [active, setActive] = React.useState({
    name: 'to-dos'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return (
    <div className="d-flex align-items-center py-6 bg-secondary-lightest">
      <HorizontalNav
        className="w-100 justify-content-center"
        menus={data}
        active={active}
        onClick={onClickHandler}
      />
    </div>
  );
}
```


#### Components HorizontalNav Variants With Icon

```jsx
import { HorizontalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'text',
      label: 'Text',
      icon: 'message'
    },
    {
      name: 'voice',
      label: 'Voice',
      icon: 'mic'
    },
    {
      name: 'mail',
      label: 'Mail',
      icon: 'email'
    },
  ];

  const [active, setActive] = React.useState({
    name: 'text'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return (
    <div className="d-flex align-items-center py-6 bg-secondary-lightest">
      <HorizontalNav
        className="w-100 justify-content-center"
        menus={data}
        active={active}
        onClick={onClickHandler}
      />
    </div>
  );
}
```


#### Components HorizontalNav With Animation

```jsx
import { Card, Table, Text, Button, List, HorizontalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'menu_1',
      label: 'Menu 1',
      count: 20,
    },
    {
      name: 'menu_2',
      label: 'Menu 2',
      count: 10
    },
    {
      name: 'menu_3',
      label: 'Menu 3',
      disabled: true,
      count: 5,
    }
  ];

  const [menu, setActiveMenu] = React.useState({
    name: 'menu_1',
  });
  const [active, setActive] = React.useState({
    name: 'menu_1',
  });

  const handleAnimationEnd = () => {
    setActive(menu);
  }

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActiveMenu(menu);
  };

  const getMenu1List = (active, menu, handleAnimationEnd) => {

    const data = [
      {
        name: 'MSSP Track 1 Urban',
        status: 'Active',
        measures: '9',
        current_period: 'March 2017 - Feb 2018',
        added_in: 'March 2014',
      },
      {
        name: 'MSSP Track 1 Rural',
        status: 'Active',
        measures: '9',
        current_period: 'March 2017 - Feb 201',
        added_in: 'March 2015',
      },
      {
        name: 'MSSP Track 2',
        status: 'Inactive',
        measures: '14',
        current_period: 'March 2017 - Feb 201',
        added_in: 'March 2016',
      },
      {
        name: 'Aetna',
        status: 'Active',
        measures: '20',
        current_period: 'March 2017 - Feb 201',
        added_in: 'March 2019',
      },
      {
        name: 'BCBS',
        status: 'Active',
        measures: '16',
        current_period: 'March 2017 - Feb 201',
        added_in: 'March 2017',
      },
    ];
  
    const schema = [
      {
        name: 'name',
        displayName: 'Name',
        width: '20%',
        sorting: false,
      },
      {
        name: 'status',
        displayName: 'Status',
        width: '20%',
        translate: (a) => ({
          title: a.status,
          statusAppearance: a.status === 'Inactive' ? 'default' : 'success',
        }),
        cellType: 'STATUS_HINT',
        sorting: false,
      },
      {
        name: 'measures',
        displayName: 'No. of Measures',
        width: '20%',
        sorting: false,
      },
      {
        name: 'current_period',
        displayName: 'Current Period',
        width: '20%',
        sorting: false,
      },
      {
        name: 'added_in',
        displayName: 'Added in',
        width: '20%',
        sorting: false,
      },
    ];
  
    return (
      <Card
        onAnimationEnd={handleAnimationEnd}
        className={`${menu.name != active.name ? 'slideOut-left' : 'slideIn-left'} pt-4`}
      >
        <Table
          size="compressed"
          showMenu={false}
          separator={false}
          data={data}
          schema={schema}
          withHeader={true}
          withPagination={false}
          headerOptions={{ withSearch: true, }}
          onSearch={(currData, searchTerm) => {
            return currData.filter((d) => d.name.toLowerCase().match(searchTerm.toLowerCase()));
          }}
        />
      </Card>
    )
  }

  const getMenu2List = (active, menu, handleAnimationEnd) => {
    const data = [
      {
        firstName: 'John',
        lastName: 'Doe',
        email: 'jonathandoe@gamil.com',
        owner: true
      },
      {
        firstName: 'Katty',
        lastName: 'Perry',
        email: 'kattyperry21@gamil.com',
        edit: true
      },
      {
        firstName: 'Daniel',
        lastName: 'Low',
        email: 'daniellow02@yahoo.com',
        view: true
      },
    ];
  
    const schema = [
      {
        name: 'info',
        displayName: 'Info',
        width: '80%',
        cellType: 'AVATAR_WITH_META_LIST',
        translate: a => ({
          firstName: a.firstName,
          lastName: a.lastName,
          title: `${a.firstName} ${a.lastName}`,
          metaList: [a.email]
        }),
      },
      {
        name: 'rights',
        displayName: 'Rights',
        width: '20%',
        cellRenderer: (props) => {
          const renderRights = () => {
            if (props.data.owner) {
              return <Text appearance="subtle" className="pr-5">owner</Text>;
            }
  
            if (props.data.edit || props.data.view) {
              const rights = props.data.edit ? 'edit' : 'view';
              return (
                <Button
                  icon="keyboard_arrow_down"
                  iconAlign="right"
                  appearance="transparent"
                  onClick={e => e.stopPropagation()}
                >
                  {`can ${rights}`}
                </Button>
              );
            }
  
            return null;
          };
  
          return (
            <div className="d-flex align-items-center justify-content-end flex-grow-1">
              {renderRights()}
            </div>
          );
        }
      }
    ];
  
    return (
        <Card 
          onAnimationEnd={handleAnimationEnd}
          className={`${menu.name != active.name ? 'slideOut-left' : 'slideIn-left'} pt-4`}
        >
          <Text size="large" weight="strong" className="ml-5">Sharing Test Manual</Text>
          <List
            type="resource"
            withHeader={true}
            headerOptions={{
              withSearch: true,
              dynamicColumn: false
            }}
            separator={false}
            showMenu={false}
            data={data}
            schema={schema}
            withPagination={false}
            onSearch={(currData, searchTerm) => {
              return currData.filter(d =>
                d.firstName.toLowerCase().match(searchTerm.toLowerCase())
                || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
              );
            }}
            onRowClick={(rowData, rowIndex) =>
              console.log(`o
-row-click:- rowIndex: ${rowIndex} data: ${JSON.stringify(rowData)}`)
            }
          />
        </Card>
    );
  };

  return (
    <div className='bg-secondary-lightest h-100 p-5 border-top border-bottom'>
      <HorizontalNav
        className="w-100 pb-5 mb-5 justify-content-center border-bottom"
        menus={data}
        active={menu}
        onClick={onClickHandler}
      />

      {active.name === 'menu_1' ?
        getMenu1List(active, menu, handleAnimationEnd)
        :
        getMenu2List(active, menu, handleAnimationEnd)
      }
    </div>
  );
}
```# Icon



### Code Examples

#### Components Icon All

```jsx
import { Icon } from '@innovaccer/design-system';

() => {
  return(
    <Icon size={48} name='place'/>
    );
}
```


#### Icon

```jsx
import { Icon, Text } from '@innovaccer/design-system';

() => {
  const appearances = [
    ['primary', 'primary_dark', 'primary_darker', 'primary_lighter'],
    ['alert', 'alert_dark', 'alert_darker', 'alert_lighter'],
    ['success', 'success_dark', 'success_darker', 'success_lighter'],
    ['warning', 'warning_dark', 'warning_darker', 'warning_lighter'],
    ['accent1', 'accent1_dark', 'accent1_darker', 'accent1_lighter'],
    ['accent2', 'accent2_dark', 'accent2_darker', 'accent2_lighter'],
    ['accent3', 'accent3_dark', 'accent3_darker', 'accent3_lighter'],
    ['accent4', 'accent4_dark', 'accent4_darker', 'accent4_lighter'],
    ['inverse', 'subtle', 'disabled'],
  ];

  const name = 'events';
  return (
    <div>
      {appearances.map((appearance, ind) => {
        return (
          <div key={ind} className="d-flex mb-8">
            <div>
              <Icon className="mr-12 mb-4" appearance={appearance[0]} size={48} name={name} />
              <br />
              <Text weight="strong">{appearance[0]}</Text>
            </div>

            <div>
              <Icon className="mr-12 mb-4" appearance={appearance[1]} size={48} name={name} />
              <br />
              <Text weight="strong">{appearance[1]}</Text>
            </div>

            <div>
              <Icon className="mr-12 mb-4" appearance={appearance[2]} size={48} name={name} />
              <br />
              <Text weight="strong">{appearance[2]}</Text>
            </div>

            {appearance[3] && (
              <div>
                <Icon className="mb-4" appearance={appearance[3]} size={48} name={name} />
                <br />
                <Text weight="strong">{appearance[3]}</Text>
              </div>
            )}
          </div>
        );
      })}
      <div>
        <Icon appearance="white" size={48} name={name} className="bg-dark" />
      </div>
      <br />
      <Text weight="strong">white</Text>
      <div className="mt-5">
        <Icon appearance="destructive" size={48} name={name} />
      </div>
      <br />
      <Text weight="strong">destructive</Text>
    </div>
  );
}
```


#### Icon

```jsx
import { Icon } from '@innovaccer/design-system';

() => {
  return (
    <Icon size={48}>
      <img alt="Innovaccer logo" src="https://design.innovaccer.com/images/withoutType.png" width="48" height="48" />
    </Icon>
  );
}
```


#### Icon

```jsx
import { Icon, Text } from '@innovaccer/design-system';

() => {
  const types = ['outlined', 'rounded'];

  const name = 'alarm';
  return (
    <div className="d-flex">
      {types.map((IconShape, ind) => {
        return (
          <div key={ind} className="mr-10">
            <Icon type={IconShape} size={48} name={name} />
            <br />
            <Text weight="strong">{IconShape.charAt(0).toUpperCase() + IconShape.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```# InlineMessage



### Code Examples

#### Components InlineMessage All

```jsx
import { InlineMessage } from '@innovaccer/design-system';

() => {
  return <InlineMessage appearance="info" description="There are two new referral requests." />;
}
```


#### Components InlineMessage Appearance Alert

```jsx
import { InlineMessage } from '@innovaccer/design-system';

() => <InlineMessage appearance="alert" description="Inline message goes here." />
```


#### Components InlineMessage Appearance Info

```jsx
import { InlineMessage } from '@innovaccer/design-system';

() => <InlineMessage appearance="info" description="There are two new referral requests." />
```


#### Components InlineMessage Appearance Success

```jsx
import { InlineMessage } from '@innovaccer/design-system';

() => <InlineMessage appearance="success" description="Inline message goes here." />
```


#### Components InlineMessage Appearance Warning

```jsx
import { InlineMessage } from '@innovaccer/design-system';

() => <InlineMessage appearance="warning" description="Inline message goes here." />
```


#### Components InlineMessage Inline Message Within Table

```jsx
import { InlineMessage, Card, Table } from '@innovaccer/design-system';


() => {
  const data = [
    {
        "name": "Asthma Outreach",
        "firstName": "Brooke",
        "lastName": "Heeran",
        "lastUpdated": "June 20, 2020",
        "recipients": 11846
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "lastUpdated": "June 19, 2020",
        "name": "HbA1c Test due",
        "recipients": 12846
    },
    {
        "firstName": "Lemmie",
        "name": "ER Education",
        "lastName": "Ciric",
        "lastUpdated": "May 19, 2020",
        "recipients": 118467
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '30%',
      cellType: 'WITH_META_LIST',
      sorting: false,
      translate: (a) => ({
        title: a.name,
        metaList: [`${a.recipients} recipients`]
      }),
    },
    {
      name: 'lastUpdated',
      displayName: 'Last Updated on',
      width: '30%',
      sorting: false,
    },
    {
      name: 'user',
      displayName: 'Message',
      sorting: false,
      width: '40%',
      cellRenderer: (props) => {
        const { data } = props;
        return (
          <InlineMessage appearance='info' description='Patient profile updated.' />
        );
      }
    }
  ];

  return (
    <Card>
      <Table
        showMenu={false}
        type="data"
        data={data}
        schema={schema}
        withHeader={false}
        headerOptions={{
          withSearch: false
        }}
      />
    </Card>
  );
};

```


#### Components InlineMessage Size

```jsx
import { InlineMessage, Text } from '@innovaccer/design-system';

() => {
  const sizes = ['small', 'regular'];

  return (
    <div className="d-flex align-items-center">
      {sizes.map((size, key) => {
        return (
          <div className="mr-9" key={key}>
            <InlineMessage size={size} appearance="info" description="There are two new referral requests." />
            <br />
            <Text weight="strong">{size.charAt(0).toUpperCase() + size.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```# Input



### Code Examples

#### Input

```jsx
import { Input } from '@innovaccer/design-system';

() => {
  const inputType = 'url';

  const placeholder = 'Placeholder';

  const info = 'sample info tooltip';

  const min = 1;

  const max = 30;

  const minLength = 1;

  const maxLength = 30;

  return (
    <Input
      className="w-25"
      name="input"
      type={inputType}
      placeholder={placeholder}
      onChange={action('on-change')}
      info={info}
      min={min}
      max={max}
      minLength={minLength}
      maxLength={maxLength}
    />
  );
}
```


#### Input

```jsx
import { Input } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState('Joy Lawson');

  const onChange = React.useCallback((e) => {
    setValue(e.target.value);
  }, []);

  const onClear = React.useCallback(() => {
    setValue('');
  }, []);

  return (
    <Input
      placeholder="Name"
      name="input"
      className="w-25"
      value={value}
      onChange={onChange}
      onClear={onClear}
    />
  );
}
```


#### Input

```jsx
import { Input } from '@innovaccer/design-system';

() => (
  <Input name="input" placeholder="Search" className="w-25" onChange={action('on-change')} icon="search" />
)
```


#### Input

```jsx
import { Label, Input, HelpText } from '@innovaccer/design-system';

() => {
  const [visibility, setVisibility] = React.useState(false);
  const [visibility2, setVisibility2] = React.useState(false);
  const [inputValue, setInputValue] = React.useState('Value');
  const [secondInputValue, setSecondInputValue] = React.useState('Value');
  return (
    <div className="d-flex">
      <div>
        <Label htmlFor="password-1" withInput={true}>
          Password
        </Label>
        <Input
          id="password-1"
          placeholder="Password"
          value={inputValue}
          type={visibility ? 'text' : 'password'}
          onChange={(ev) => {
            ev.persist();
            setInputValue(ev.target.value);
          }}
          actionIcon={
            <Input.ActionButton
              aria-label={visibility ? 'Show Password' : 'Hide Password'}
              onClick={() => setVisibility((x) => !x)}
              name={visibility ? 'visibility_on' : 'visibility_off'}
              className="cursor-pointer"
            />
          }
        />
        <HelpText message={'Create a string, unique password'} />
      </div>
      <div className="ml-6">
        <Label htmlFor="password-2" withInput={true}>
          Password
        </Label>
        <Input
          id="password-2"
          placeholder="Password"
          value={secondInputValue}
          type={visibility2 ? 'text' : 'password'}
          onChange={(ev) => {
            ev.persist();
            setSecondInputValue(ev.target.value);
          }}
          actionIcon={
            <Input.ActionButton
              aria-label={visibility ? 'Show Password' : 'Hide Password'}
              onClick={() => setVisibility2((x) => !x)}
              name={visibility2 ? 'visibility_on' : 'visibility_off'}
              className="cursor-pointer"
            />
          }
        />
        <HelpText error={true} message={'Create a password with at least 8 characters'} />
      </div>
    </div>
  );
};
```


#### Input

```jsx
import { Label, Input } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState('lawsonjoy@gmail.com');

  const onChange = React.useCallback((e) => {
    setValue(e.target.value)
  }, []);

  return (
    <>
      <Label 
        withInput={true}
        htmlFor="email"
      >
        Email
      </Label>
      <Input
        name="input"
        className="w-25"
        value={value}
        onChange={onChange}
        placeholder="Email"
      />
    </>
  );
}
```


#### Input

```jsx
import { Label, Input } from '@innovaccer/design-system';

() => {
  const [inputValue, setInputValue] = React.useState('Joy Lawson');
  const [secondInputValue, setSecondInputValue] = React.useState('Joy Lawson');
  return (
    <div className="d-flex align-items-end">
      <div>
        <Label htmlFor="fullName" withInput={true}>
          Full Name
        </Label>
        <Input
          placeholder="Full name"
          id="fullName"
          value={inputValue}
          onChange={(ev) => {
            ev.persist();
            setInputValue(ev.target.value);
          }}
        />
      </div>
      <div className="d-flex align-items-center ml-9">
        <Label htmlFor="fullName2" className="mr-6">
          Full Name
        </Label>
        <Input
          placeholder="Full name"
          id="fullName2"
          value={secondInputValue}
          onChange={(ev) => {
            ev.persist();
            setSecondInputValue(ev.target.value);
          }}
        />
      </div>
    </div>
  );
};
```


#### Input

```jsx
import { Label, Input, Text } from '@innovaccer/design-system';

() => {
  return (
    <div>
      <div className="d-flex">
        <div>
          <Label htmlFor="email" withInput={true} required={true}>
            Email
          </Label>
          <Input id="email" required placeholder="e.g lawsonjoy@gmail.com" />
          <div className="d-flex align-items-center justify-content-center mt-5">
            <Text weight="medium">Required Field</Text>
          </div>
        </div>
        <div className="ml-9">
          <Label htmlFor="email2" withInput={true}>
            Email
          </Label>
          <Input id="email2" placeholder="e.g lawsonjoy@gmail.com" />
          <div className="d-flex align-items-center justify-content-center mt-5">
            <Text weight="medium">Optional Field</Text>
          </div>
        </div>
      </div>
      <div className="d-flex mt-9">
        <div>
          <Label htmlFor="email3" withInput={true}>
            Email
          </Label>
          <Input id="email3" placeholder="e.g lawsonjoy@gmail.com" />
          <div className="d-flex align-items-center justify-content-center mt-5">
            <Text weight="medium">Required Field</Text>
          </div>
        </div>
        <div className="ml-9">
          <Label htmlFor="email4" withInput={true} optional={true}>
            Email
          </Label>
          <Input id="email4" placeholder="e.g lawsonjoy@gmail.com" />
          <div className="d-flex align-items-center justify-content-center mt-5">
            <Text weight="medium">Optional Field</Text>
          </div>
        </div>
      </div>
    </div>
  );
}
```


#### Components Input Input Variants Action Icon

```jsx
import { Input } from '@innovaccer/design-system';

() => {
  const actionIcon = (
    <Input.ActionButton name="events" onClick={() => console.log("Custom action icon")} />
  );

  return (
    <Input
      name="input"
      defaultValue="Custom action icon"
      actionIcon={actionIcon}
    />
  );
}
```


#### Input

```jsx
import { Row, Column, Input } from '@innovaccer/design-system';

() => {
  const [visibility, setVisibility] = React.useState(false);
  const [value, setValue] = React.useState('Value');
  const handleParentChange = (event) => {
    const updatedValue = event.target.value;
      setValue(updatedValue);
  };
  const [value1, setValue1] = React.useState('Value');
  const onChangeHandler = (event) => {
    const updatedValue = event.target.value;
      setValue1(updatedValue);
  };
  const onClearHandler = () => {
    const updatedValue = '';
      setValue1(updatedValue);
  };
  return (
    <Row>
    <Column size={4}>
      <Input
        name="input"
        value={value}
        type={visibility ? 'text' : 'password'}
        placeholder="Placeholder"
        actionIcon={
          <Input.ActionButton
            onClick={() => {
              setVisibility((x) => !x);
            }}
            name={visibility ? 'visibility_on' : 'visibility_off'}
            aria-label={visibility ? 'Show Password' : 'Hide Password'}
            className="cursor-pointer"
          />
        }
        onChange={handleParentChange}
      />
    </Column>
    <Column size={4} className="ml-7">
      <Input
        name="input"
        value={value1}
        type="text"
        placeholder="PlaceHolder"
        onChange={onChangeHandler}
        onClear={onClearHandler}
      />
    </Column>
  </Row>
  );
};
```


#### Input

```jsx
import { Label, Input } from '@innovaccer/design-system';

() => {
  const sizes = ['tiny', 'regular', 'large'];

  const placeholder = 'Placeholder';

  return (
    <div>
      {sizes.map((InputSize, ind) => {
        return (
          <div key={ind} className="mb-8 w-25">
            <Label htmlFor={InputSize} withInput={true}>
              {InputSize.charAt(0).toUpperCase() + InputSize.slice(1)}
            </Label>
            <Input name="input" onChange={action('on-change')} placeholder={placeholder} size={InputSize} />
          </div>
        );
      })}
    </div>
  );
}
```


#### Input

```jsx
import { Input, Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="Row">
      <div className="mr-9 mb-8 w-25">
        <Input name="input" placeholder="Placeholder" onChange={action('on-change')} />
        <br />
        <Text weight="strong">Default</Text>
      </div>
      <div className="mr-9 mb-8 w-25">
        <Input
          name="input"
          value=""
          placeholder="Placeholder"
          onChange={action('on-change')}
          info="sample info tooltip"
        />
        <br />
        <Text weight="strong">Placeholder</Text>
      </div>
      <div className="mr-9 mb-8 w-25">
        <Input name="input" placeholder="Placeholder" onChange={action('on-change')} error={true} />
        <br />
        <Text weight="strong">Error</Text>
      </div>
      <div className="mr-9 w-25">
        <Input name="input" placeholder="Placeholder" disabled={true} />
        <br />
        <Text weight="strong">Disabled</Text>
      </div>
      <div className="mr-9 w-25">
        <Input name="input" value="Value" readOnly={true} />
        <br />
        <Text weight="strong">Read Only</Text>
      </div>
    </div>
  );
}
```


#### Input

```jsx
import { Input, Text } from '@innovaccer/design-system';

() => {
  const icon = 'search';
  return (
    <div className="Row">
      <div className="mr-9 mb-8 w-25">
        <Input name="input" placeholder="Search" onChange={action('on-change')} icon={icon} />
        <br />
        <Text weight="strong">Default</Text>
      </div>
      <div className="mr-9 mb-8 w-25">
        <Input
          name="input"
          placeholder="Search"
          onChange={action('on-change')}
          info="sample info tooltip"
          icon={icon}
        />
        <br />
        <Text weight="strong">Placeholder</Text>
      </div>
      <div className="mr-9 mb-8 w-25">
        <Input name="input" placeholder="Search" onChange={action('on-change')} error={true} icon={icon} />
        <br />
        <Text weight="strong">Error</Text>
      </div>
      <div className="mr-9 w-25">
        <Input name="input" placeholder="Search" disabled={true} icon={icon} />
        <br />
        <Text weight="strong">Disabled</Text>
      </div>
      <div className="mr-9 w-25">
        <Input name="input" value="Value" icon={icon} readOnly={true} />
        <br />
        <Text weight="strong">Read Only</Text>
      </div>
    </div>
  );
}
```# InputMask



### Code Examples

#### Components Input InputMask All

```jsx
import { InputMask } from '@innovaccer/design-system';

// import { Utils } from '@innovaccer/design-system';

() => {
  const dateMask = Utils.masks.date['mm/dd/yyyy'];
  const dateValidator = (val) => Utils.validators.date(val, 'mm/dd/yyyy');

  return (
    <div className="w-25">
      <InputMask
        icon="calendar_month"
        mask={dateMask}
        validators={dateValidator}
        placeholder="mm/dd/yyyy"
      />
    </div>
  );
};

```


#### Components Input InputMask Card Number

```jsx
import { Label, InputMask } from '@innovaccer/design-system';

() => {
  return (
    <div className="w-25">
      <Label className="mb-3">Card Number</Label>
      <InputMask
        mask={[
          /\d/,
          /\d/,
          /\d/,
          /\d/,
          ' ',
          /\d/,
          /\d/,
          /\d/,
          /\d/,
          ' ',
          /\d/,
          /\d/,
          /\d/,
          /\d/,
          ' ',
          /\d/,
          /\d/,
          /\d/,
          /\d/,
        ]}
        placeholder="____ ____ ____ ____"
        name="card_number"
        icon="credit_card"
      />
    </div>
  );
}
```


#### InputMask

```jsx
import { Row, Label, InputMask } from '@innovaccer/design-system';

() => {
  const ref = React.useRef(null);
  const [error, setError] = React.useState(false);

  const onChangeHandler = () => {
    setError(ref.current.value[1] === '0');
  };

  return (
    <Row className="w-25 d-flex">
      <div>
        <Label withInput={true}>Phone Number</Label>
        <InputMask
          icon="call"
          name="primary_phone"
          placeholder="(___) ___-____"
          helpText="Enter your phone number"
          mask={['(', /[1-9]/, /\d/, /\d/, ')', ' ', /\d/, /\d/, /\d/, '-', /\d/, /\d/, /\d/, /\d/]}
        />
      </div>

      <div className="mt-8">
        <Label withInput={true}>Phone Number</Label>
        <InputMask
          ref={ref}
          icon="call"
          error={error}
          onChange={onChangeHandler}
          name="primary_phone"
          placeholder="(___) ___-____"
          helpText="Enter a phone number starting 0 to see the error mode"
          caption="Phone number cannot start with 0"
          mask={['(', /\d/, /\d/, /\d/, ')', ' ', /\d/, /\d/, /\d/, '-', /\d/, /\d/, /\d/, /\d/]}
        />
      </div>
    </Row>
  );
};
```# KeyValuePair

Key value pairs consist of properties (keys) each paired with their respective values.

### Code Examples

#### Components KeyValuePair All

```jsx
import { Text, KeyValuePair } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex justify-content-between w-75">
      <div>
        <Text weight="strong">Left Right Arrangement</Text>
        <KeyValuePair className="d-flex mt-8">
          <KeyValuePair.Key className="mr-7" icon="call" label="Phone" />
          <KeyValuePair.Value value="(555) 555-5555" />
        </KeyValuePair>
      </div>
      <div>
        <Text weight="strong">Top Bottom Arrangement</Text>
        <KeyValuePair className="mt-8">
          <KeyValuePair.Key label="Name" />
          <KeyValuePair.Value value="Joy Lawson" />
        </KeyValuePair>
      </div>
    </div>
  );
}
```


#### Components KeyValuePair Arrangement Left Right Arrangement

```jsx
import { Card, CardHeader, Heading, CardBody, KeyValuePair, Column, StatusHint, MetaList, Avatar, Text, Icon, Badge } from '@innovaccer/design-system';

() => {
  return (
    <Card className="w-50" shadow="none">
      <CardHeader>
        <Heading size="s">Case details</Heading>
      </CardHeader>

      <CardBody className="pb-6">
        <KeyValuePair className="d-flex">
          <Column size={5} className="pr-7">
            <KeyValuePair.Key label="Status" />
          </Column>
          <Column size={7}>
            <KeyValuePair.Value>
              <StatusHint appearance="info">Status Hint</StatusHint>
              <MetaList list={[{ label: 'Just now' }, { label: 'Clinical' }]} />
            </KeyValuePair.Value>
          </Column>
        </KeyValuePair>

        <KeyValuePair className="d-flex mt-5">
          <Column size={5} className="pr-7">
            <KeyValuePair.Key label="Assigned to" />
          </Column>
          <Column size={7}>
            <KeyValuePair.Value className="d-flex align-items-center">
              <Avatar appearance="primary" firstName="Molly" lastName="Daniels" size="tiny" />
              <Text className="ml-4">Daniels, Molly</Text>
            </KeyValuePair.Value>
          </Column>
        </KeyValuePair>

        <KeyValuePair className="d-flex mt-5">
          <Column size={5} className="pr-7">
            <KeyValuePair.Key label="Referred on" />
          </Column>
          <Column size={7}>
            <KeyValuePair.Value className="d-flex align-items-center">
              <Icon name="event" className="my-2" />
              <Text className="ml-3">08/23/2023</Text>
            </KeyValuePair.Value>
          </Column>
        </KeyValuePair>

        <KeyValuePair className="d-flex mt-5">
          <Column size={5} className="pr-7">
            <KeyValuePair.Key label="All programs" />
          </Column>
          <Column size={7}>
            <KeyValuePair.Value className="d-flex align-items-center">
              <Badge>Asthma</Badge>
              <Badge className="ml-4">HIV</Badge>
              <Badge className="ml-4">Hepatitis</Badge>
            </KeyValuePair.Value>
          </Column>
        </KeyValuePair>
      </CardBody>
    </Card>
  )
}
```


#### Components KeyValuePair Arrangement Top Bottom Arrangement

```jsx
import { Card, Heading, KeyValuePair, Avatar, Text } from '@innovaccer/design-system';

() => {
  const healthRecordList = [
    { key: 'TIN', value: '879-79-7989' },
    { key: 'Location', value: 'San Diego, California' },
    { key: 'PCPs', value: '2' },
    { key: 'Risk score', value: '1.5' },
    { key: 'Assignee', value: 'Joy Lawson', showAvatar: true },
    { key: 'Quality score', value: '89' },
    { key: 'Patient count', value: '590' },
  ];

  return (
    <Card className="p-6" shadow="none">
      <Heading size="s">Health center</Heading>
      <div className="d-flex justify-content-between mt-4">
        {healthRecordList.map((healthRecord) => {
          return (
            <KeyValuePair key={healthRecord}>
              <KeyValuePair.Key label={healthRecord.key} />
              <KeyValuePair.Value value={healthRecord.value}>
                {healthRecord.showAvatar && (
                  <div className="mt-3 d-flex align-items-center">
                    <Avatar appearance="primary" firstName="Joy" lastName="Lawson" size="tiny" />
                    <Text className="ml-4">{healthRecord.value}</Text>
                  </div>
                )}
              </KeyValuePair.Value>
            </KeyValuePair>
          );
        })}
      </div>
    </Card>
  );
}
```


#### Components KeyValuePair Multiple Column Layout Column With Fixed Width

```jsx
import { Card, Row, Column, KeyValuePair, StatusHint, LinkButton } from '@innovaccer/design-system';

() => {
  return (
    <div>
      <Card className="px-6 py-7" shadow="none">
        <Row className="d-flex justify-content-between">
          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="Provider" />
              <KeyValuePair.Value value="Dr. Anil Jain" />
            </KeyValuePair>
          </Column>

          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="TIN" />
              <KeyValuePair.Value value="879-79-7989" />
            </KeyValuePair>
          </Column>

          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="Location" />
              <KeyValuePair.Value value="San Diego, California" />
            </KeyValuePair>
          </Column>

          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="Quality score" />
              <KeyValuePair.Value value="89" />
            </KeyValuePair>
          </Column>
        </Row>

        <Row className="mt-6 d-flex justify-content-between">
          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="PCPs" />
              <KeyValuePair.Value value="2" />
            </KeyValuePair>
          </Column>

          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="Risk score" />
              <KeyValuePair.Value value="1.5" />
            </KeyValuePair>
          </Column>

          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="Patient count" />
              <KeyValuePair.Value value="590" />
            </KeyValuePair>
          </Column>

          <Column size={2} />
        </Row>
      </Card>

      <Card className="px-6 py-7 mt-6" shadow="none">
        <Row className="d-flex justify-content-between">
          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="Ticket type" />
              <KeyValuePair.Value value="Appointment request" />
            </KeyValuePair>
          </Column>

          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="Channel" />
              <KeyValuePair.Value value="Text Message" />
            </KeyValuePair>
          </Column>

          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="Transfer status" />
              <KeyValuePair.Value>
                <StatusHint appearance="success">Complete</StatusHint>
              </KeyValuePair.Value>
            </KeyValuePair>
          </Column>

          <Column size={2}>
            <KeyValuePair>
              <KeyValuePair.Key label="Location" />
              <KeyValuePair.Value>
                <LinkButton>Add</LinkButton>
              </KeyValuePair.Value>
            </KeyValuePair>
          </Column>
        </Row>
      </Card>
    </div>
  );
}
```


#### Components KeyValuePair Multiple Column Layout Column With Variable Width

```jsx
import { Card, KeyValuePair } from '@innovaccer/design-system';

() => {
  return (
    <div>
      <Card className="px-6 py-7" shadow="none">
        <div className="d-flex justify-content-between w-50">
          <KeyValuePair className="d-flex flex-column">
            <KeyValuePair.Key label="Provider" />
            <KeyValuePair.Value value="Dr. Anil Jain" />
          </KeyValuePair>
          <KeyValuePair className="d-flex flex-column">
            <KeyValuePair.Key label="Score" />
            <KeyValuePair.Value value="89" />
          </KeyValuePair>
          <KeyValuePair className="d-flex flex-column">
            <KeyValuePair.Key label="TIN" />
            <KeyValuePair.Value value="879-79-7989" />
          </KeyValuePair>
          <KeyValuePair className="d-flex flex-column">
            <KeyValuePair.Key label="Location" />
            <KeyValuePair.Value value="San Diego, California" />
          </KeyValuePair>
        </div>
      </Card>
    </div>
  );
}
```


#### Components KeyValuePair Width Left Right Width

```jsx
import { Text, Card, CardHeader, Heading, CardBody, KeyValuePair, Column, StatusHint, MetaList, Avatar, Icon, Badge } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex justify-content-between">
      <div className="w-50 pr-10">
        <Text weight="strong">40:60 Key-Value Width Ratio (Recommended)</Text>
        <Card className="mt-5" shadow="none">
          <CardHeader>
            <Heading size="s">Case details</Heading>
          </CardHeader>

          <CardBody className="pb-6">
            <KeyValuePair className="d-flex">
              <Column size={5} className="pr-7">
                <KeyValuePair.Key label="Status" />
              </Column>
              <Column size={7}>
                <KeyValuePair.Value className="flex-column">
                  <StatusHint appearance="info">Status Hint</StatusHint>
                  <MetaList list={[{ label: 'Just now' }, { label: 'Clinical' }]} />
                </KeyValuePair.Value>
              </Column>
            </KeyValuePair>

            <KeyValuePair className="d-flex mt-5">
              <Column size={5} className="pr-7">
                <KeyValuePair.Key label="Assigned to" />
              </Column>
              <Column size={7}>
                <KeyValuePair.Value className="d-flex align-items-center">
                  <Avatar appearance="primary" firstName="Molly" lastName="Daniels" size="tiny" />
                  <Text className="ml-4">Daniels, Molly</Text>
                </KeyValuePair.Value>
              </Column>
            </KeyValuePair>

            <KeyValuePair className="d-flex mt-5">
              <Column size={5} className="pr-7">
                <KeyValuePair.Key label="Referred on" />
              </Column>
              <Column size={7}>
                <KeyValuePair.Value className="d-flex align-items-center">
                  <Icon name="event" className="my-2" />
                  <Text className="ml-3">08/23/2023</Text>
                </KeyValuePair.Value>
              </Column>
            </KeyValuePair>

            <KeyValuePair className="d-flex mt-5">
              <Column size={5} className="pr-7">
                <KeyValuePair.Key label="All programs" />
              </Column>
              <Column size={7}>
                <KeyValuePair.Value className="d-flex align-items-center">
                  <Badge>Asthma</Badge>
                  <Badge className="ml-4">HIV</Badge>
                  <Badge className="ml-4">Hepatitis</Badge>
                </KeyValuePair.Value>
              </Column>
            </KeyValuePair>

            <KeyValuePair className="d-flex mt-5">
              <Column size={5} className="pr-7">
                <KeyValuePair.Key label="Additional given comments" />
              </Column>
              <Column size={7}>
                <KeyValuePair.Value value="Patient visited the clinic and requested an appointment." />
              </Column>
            </KeyValuePair>
          </CardBody>
        </Card>
      </div>

      <div className="w-50">
        <Text weight="strong">50:50 Key-Value Width Ratio</Text>
        <Card className="mt-5" shadow="none">
          <CardHeader>
            <Heading size="s">Case details</Heading>
          </CardHeader>

          <CardBody className="pb-6">
            <KeyValuePair className="d-flex">
              <Column size={6} className="pr-7">
                <KeyValuePair.Key label="Status" />
              </Column>
              <Column size={6}>
                <KeyValuePair.Value className="flex-column">
                  <StatusHint appearance="info">Status Hint</StatusHint>
                  <MetaList list={[{ label: 'Just now' }, { label: 'Clinical' }]} />
                </KeyValuePair.Value>
              </Column>
            </KeyValuePair>

            <KeyValuePair className="d-flex mt-5">
              <Column size={6} className="pr-7">
                <KeyValuePair.Key label="Assigned to" />
              </Column>
              <Column size={6}>
                <KeyValuePair.Value className="d-flex align-items-center">
                  <Avatar appearance="primary" firstName="Molly" lastName="Daniels" size="tiny" />
                  <Text className="ml-4">Daniels, Molly</Text>
                </KeyValuePair.Value>
              </Column>
            </KeyValuePair>

            <KeyValuePair className="d-flex mt-5">
              <Column size={6} className="pr-7">
                <KeyValuePair.Key label="Referred on" />
              </Column>
              <Column size={6}>
                <KeyValuePair.Value className="d-flex align-items-center">
                  <Icon name="event" className="my-2" />
                  <Text className="ml-3">08/23/2023</Text>
                </KeyValuePair.Value>
              </Column>
            </KeyValuePair>

            <KeyValuePair className="d-flex mt-5">
              <Column size={6} className="pr-7">
                <KeyValuePair.Key label="All programs" />
              </Column>
              <Column size={6}>
                <KeyValuePair.Value className="d-flex align-items-center">
                  <Badge>Asthma</Badge>
                  <Badge className="ml-4">HIV</Badge>
                  <Badge className="ml-4">Hepatitis</Badge>
                </KeyValuePair.Value>
              </Column>
            </KeyValuePair>

            <KeyValuePair className="d-flex mt-5">
              <Column size={6} className="pr-7">
                <KeyValuePair.Key label="Additional given comments" />
              </Column>
              <Column size={6}>
                <KeyValuePair.Value value="Patient visited the clinic and requested an appointment." />
              </Column>
            </KeyValuePair>
          </CardBody>
        </Card>
      </div>
    </div>
  );
}
```


#### Components KeyValuePair Width Top Bottom Width

```jsx
import { Card, KeyValuePair } from '@innovaccer/design-system';

() => {
  return (
    <Card className="p-7 w-25" shadow="none">
      <KeyValuePair>
        <KeyValuePair.Key label="Additional comments" />
        <KeyValuePair.Value value="Patient visited the clinic and requested an appointment." />
      </KeyValuePair>
    </Card>
  );
}
```# Label



### Code Examples

#### Label

```jsx
import { Label } from '@innovaccer/design-system';

() => {
  return <Label>Label</Label>;
}
```


#### Label

```jsx
import { Label } from '@innovaccer/design-system';

() => {
  return <Label optional={true}>Label</Label>;
}
```


#### Label

```jsx
import { Label } from '@innovaccer/design-system';

() => {
  return <Label required={true}>Required Label</Label>;
}
```


#### Label

```jsx
import { Label } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <Label className="mr-5">Enabled Label</Label>
      <Label disabled={true}>Disabled Label</Label>
    </div>
  );
}
```


#### Label

```jsx
import { Label } from '@innovaccer/design-system';

() => {
  return <Label info="Sample Info">Label</Label>;
}
```# Legend



### Code Examples

#### Components Legend All

```jsx
import { Legend } from '@innovaccer/design-system';

() => {
  return(
    <Legend iconAppearance="inverse" iconSize={14}>
    Legend
  </Legend>
    );
}
```


#### Legend

```jsx
import { Legend } from '@innovaccer/design-system';

() => {
  const appearances = [
    'primary',
    'secondary',
    'success',
    'alert',
    'warning',
    'accent1',
    'accent2',
    'accent3',
    'accent4',
    'inverse',
  ];

  return (
    <div>
      {appearances.map((appearance, i) => {
        return (
          <div key={i} className="mb-4">
            <Legend iconAppearance={appearance}>{appearance}</Legend>
          </div>
        );
      })}
    </div>
  );
}
```


#### Legend

```jsx
import { Legend } from '@innovaccer/design-system';

() => {
  const appearances = ['default', 'white', 'destructive', 'subtle', 'disabled'];
  return (
    <div>
      {appearances.map((appearance, i) => {
        return (
          <div key={i} className={`${appearance === 'white' ? 'bg-dark' : 'bg-transparent'} mb-4 w-25 `}>
            <Legend labelAppearance={appearance} iconAppearance={appearance === 'white' ? 'secondary' : 'inverse'}>
              {appearance}
            </Legend>
          </div>
        );
      })}
    </div>
  );
}
```


#### Legend

```jsx
import { Legend } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <div className="mr-5">
        <Legend labelWeight={'strong'}>Strong</Legend>
      </div>
      <div>
        <Legend labelWeight={'medium'}>Medium</Legend>
      </div>
    </div>
  );
}
```# Link



### Code Examples

#### Link

```jsx
import { Link } from '@innovaccer/design-system';

() => {
  const href = 'http://innovaccer.com';
  const target = '_blank';
  const size = 'regular';
  const disabled = false;

  const options = {
    href,
    target,
    size,
    disabled,
  };

  return (
    <Link {...options} onClick={action('link click')}>
      Read more
    </Link>
  );
}
```


#### Link

```jsx
import { Link } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <Link appearance="default" href="http://innovaccer.com">
        Default Link
      </Link>
      <Link appearance="subtle" href="http://innovaccer.com" className="ml-7">
        Subtle Link
      </Link>
    </div>
  );
}
```


#### Link

```jsx
import { Link } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <Link href="http://innovaccer.com" disabled={true}>
        Link Disabled
      </Link>
      <Link href="http://innovaccer.com" appearance="subtle" disabled={true} className="ml-7">
        Link Disabled
      </Link>
    </div>
  );
}
```


#### Link

```jsx
import { Link } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <Link href="http://innovaccer.com" size="regular">
        Regular Link
      </Link>
      <Link href="http://innovaccer.com" size="tiny" className="ml-7 mt-2">
        Tiny Link
      </Link>
    </div>
  );
}
```# LinkButton

Link button is used to initiate standalone actions in cases where using a button impacts spacing, alignment, or overall aesthetics.

### Code Examples

#### Components Button LinkButton All

```jsx
import { LinkButton } from '@innovaccer/design-system';

() => {
  const type = 'button';

  const icon = 'keyboard_arrow_down_round';

  const iconAlign = 'right';

  const children = 'more details';

  return (
    <LinkButton type={type} icon={icon} iconAlign={iconAlign} aria-label="Open" onClick={action('button-clicked')}>
      {children}
    </LinkButton>
  );
}
```


#### Components Button LinkButton Disabled

```jsx
import { LinkButton } from '@innovaccer/design-system';

() => {
  const icon = 'keyboard_arrow_down_round';
  const iconAlign = 'right';
  const children = 'more details';

  return (
    <LinkButton icon={icon} iconAlign={iconAlign} aria-label="More Details" disabled={true}>
      {children}
    </LinkButton>
  );
}
```


#### LinkButton

```jsx
import { LinkButton, Text } from '@innovaccer/design-system';

() => {
  const sizes = ['tiny', 'regular'];
  const children = 'Assign to me';

  return (
    <div className="d-flex w-25 justify-content-between">
      {sizes.map((buttonSize, ind) => {
        return (
          <div key={ind}>
            <LinkButton size={buttonSize} aria-label={`${buttonSize}`}>
              {children}
            </LinkButton>
            <br />
            <Text weight="strong">{buttonSize.charAt(0).toUpperCase() + buttonSize.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### Components Button LinkButton Subtle

```jsx
import { LinkButton } from '@innovaccer/design-system';

() => {
  const type = 'button';

  const icon = 'keyboard_arrow_down_round';

  const iconAlign = 'right';

  const children = 'more details';

  return (
    <LinkButton subtle={true} type={type} icon={icon} iconAlign={iconAlign} aria-label="Open">
      {children}
    </LinkButton>
  );
}
```


#### LinkButton

```jsx
import { LinkButton, Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <div className="mr-10">
        <LinkButton icon="add" iconAlign="left" aria-label="left">
          add items
        </LinkButton>
        <br />
        <Text weight="strong">Left</Text>
      </div>

      <div>
        <LinkButton icon="keyboard_arrow_down_round" iconAlign="right" aria-label="right">
          more details
        </LinkButton>
        <br />
        <Text weight="strong">Right</Text>
      </div>
    </div>
  );
}
```# Listbox

Related content grouped together and arranged vertically or horizontally.

### Code Examples

#### Listbox

```jsx
import { Card, CardHeader, Heading, Listbox } from '@innovaccer/design-system';

() => {
  const data = [
    {
      assessment: 'Alcohol Usage Disorders Identification Test - C (Audit C)',
    },
    {
      assessment: 'Functional Assessment - Initial',
    },
    {
      assessment: 'Functional Assessment - Discharge',
    },
    {
      assessment: 'Hypertension - Diabetes Symptoms Identification Test',
    },
    {
      assessment: 'Patient Health Question',
    },
  ];

  return (
    <Card shadow="none">
      <CardHeader>
        <Heading size="s">Select Assessment</Heading>
      </CardHeader>

      <Listbox>
        {data.map((item, key) => {
          return <Listbox.Item key={key}>{item.assessment}</Listbox.Item>;
        })}
      </Listbox>
    </Card>
  );
}
```


#### Listbox

```jsx
import { Listbox, Text, Switch, Card, Icon, MetaList, StatusHint, Dropdown, Button } from '@innovaccer/design-system';


() => {
  const SubList = () => {
    const noteList = ['Call Note', 'Visit note', 'Generic note', 'Ad-hoc task'];

    /*
      // style.css
        .SubList-wrapper {
          margin-left: 40px;
          background-color: #fcfafa;
        }

        .Listbox-wrapper {
          height: var(--spacing-9);
        }
    */

    return (
      <Listbox type="description" className="SubList-wrapper mr-6 mb-5 mt-3">
        {noteList.map((note, key) => {
          return (
            <Listbox.Item key={key} className="justify-content-between">
              <Text>{note}</Text>
              <Switch defaultChecked={true} size="tiny" />
            </Listbox.Item>
          );
        })}
      </Listbox>
    );
  };

  const [expandList, setExpandList] = React.useState([]);

  const dataList = [
    {
      title: 'Provider Chat',
      date: '09/11/2022',
      user: 'Erin Boor',
      status: 'Active',
    },
    {
      title: 'Healthwise',
      date: '09/11/2003',
      user: 'Sam',
      status: 'Active',
    },
    {
      title: 'Productivity Metrics',
      date: '09/11/2003',
      user: 'Eric Sam',
      status: 'Active',
    },
    {
      title: 'New button',
      date: '09/11/2003',
      user: 'Ashley Conner',
      status: 'Active',
    },
    {
      title: 'Timer',
      date: '09/11/2003',
      user: 'John Doe',
      status: 'Active',
    },
  ];

  const onClickHandler = (key) => {
    if (expandList.includes(key)) {
      setExpandList(expandList.filter((sid) => sid !== key));
    } else {
      let newOpen = [...expandList];
      newOpen.push(key);
      setExpandList(newOpen);
    }
  };

  return (
    <Card className="w-75" shadow="none">
      <Listbox type="description" className="Listbox-wrapper overflow-auto">
        {dataList.map((record, key) => {
          const expanded = expandList.includes(key);

          return (
            <Listbox.Item key={key} id={key} expanded={expanded} nestedBody={<SubList />}>
              <Icon
                name={'keyboard_arrow_up'}
                size={16}
                onClick={() => onClickHandler(key)}
                appearance="subtle"
                className={`mr-4 cursor-pointer ${expanded ? 'rotate-clockwise' : 'rotate-anticlockwise'}`}
              />

              <div className="d-flex w-100 justify-content-between">
                <div>
                  <Text>{record.title}</Text> <br />
                  <MetaList list={[{ label: `Updated on ${record.date}` }, { label: `Updated by ${record.user}` }]} />
                </div>

                <div className="d-flex align-items-center">
                  <StatusHint appearance="info">{record.status}</StatusHint>
                  <Dropdown
                    align="right"
                    className="ml-5"
                    menu={true}
                    customTrigger={() => <Button appearance="transparent" aria-label="Menu" icon="more_horiz" />}
                    options={[
                      { label: 'Edit', value: 'edit' },
                      { label: 'Export', value: 'export' },
                      { label: 'Delete', value: 'delete' },
                    ]}
                  />
                </div>
              </div>
            </Listbox.Item>
          );
        })}
      </Listbox>
    </Card>
  );
}

```


#### Listbox

```jsx
import { Card, Heading, Text, Divider, Listbox, Checkbox, CardFooter, Button } from '@innovaccer/design-system';

() => {
  const dataList = [
    {
      name: 'Priority',
      checked: true,
    },
    {
      name: 'Scheduled',
      checked: true,
    },
    {
      name: 'Patient',
      checked: false,
    },
    {
      name: 'Activity details',
      checked: true,
    },
    {
      name: 'Note',
      checked: true,
    },
    {
      name: 'Care gaps',
      checked: false,
    },
    {
      name: 'HHS',
      checked: true,
    },
    {
      name: 'CDPS',
      checked: true,
    },
    {
      name: 'Patient',
      checked: false,
    },
  ];

  return (
    // style.css
    // .Listbox-wrapper {
    //   height: var(--spacing-9);
    // }

    <Card className="w-50" shadow="none">
      <div className="pt-6 ml-6 mb-5">
        <Heading>Todo’s table columns</Heading>
        <Text appearance="subtle">Select the columns that you want to see in work list</Text>
      </div>
      <Divider />
      <Listbox showDivider={true} type="description" draggable={true} className="Listbox-wrapper overflow-auto">
        {dataList.map((record, key) => {
          return (
            <Listbox.Item key={key + 1} id={key + 1}>
              <div className="d-flex align-items-center w-100 justify-content-between">
                <Text>{record.name}</Text>
                <Checkbox defaultChecked={record.checked} />
              </div>
            </Listbox.Item>
          );
        })}
      </Listbox>

      <CardFooter className="bg-light justify-content-end position-relative">
        <>
          <Button appearance="basic">Cancel</Button>
          <Button appearance="primary" className="ml-4">
            Submit
          </Button>
        </>
      </CardFooter>
    </Card>
  );
}
```


#### Listbox

```jsx
import { Card, CardHeader, Heading, Listbox, Icon, Text, Badge, MetaList } from '@innovaccer/design-system';

() => {
  const dataList = [
    {
      title: 'Social Needs Assessment',
      time: '2 days ago',
      sender: 'Dr. John Matthews(your primary care physician)',
      status: 'Due',
    },
    {
      title: 'Diabetes Self Management Assessment',
      time: '1 week ago',
      sender: 'Dr. John Matthews(your primary care physician)',
    },
    {
      title: 'Depression Screening',
      time: '2 week ago',
      sender: 'Dr. Nina Locke(Psychologist)',
    },
    {
      title: 'PHQ-9 ',
      time: '1 mon ago',
      sender: 'Dr. Jimmy',
    },
  ];

  return (
    <Card shadow="none">
      <CardHeader>
        <Heading size="s">Screenings and assessments</Heading>
      </CardHeader>
      <Listbox size="compressed">
        {dataList.map((record, key) => {
          return (
            <Listbox.Item key={key}>
              <Icon name="assignment" size={20} appearance="primary" className="mr-4" />
              <div className="d-flex justify-content-between w-100 align-items-center">
                <div>
                  <div className="d-flex">
                    <Text>{record.title}</Text>
                    {record.status && (
                      <Badge appearance="alert" subtle={true} className="ml-4">
                        {record.status}
                      </Badge>
                    )}
                  </div>
                  <MetaList list={[{ label: `Sent by ${record.sender}` }, { label: `${record.time}` }]} />
                </div>
                <Icon name="chevron_right" size={20} appearance="subtle" />
              </div>
            </Listbox.Item>
          );
        })}
      </Listbox>
    </Card>
  );
}
```


#### Listbox

```jsx
import { Card, CardHeader, Heading, Listbox, Icon, Text, Badge, MetaList } from '@innovaccer/design-system';

() => {
  const dataList = [
    {
      title: 'Social Needs Assessment',
      time: '2 days ago',
      sender: 'Dr. John Matthews(your primary care physician)',
      status: 'Due',
    },
    {
      title: 'Diabetes Self Management Assessment',
      time: '1 week ago',
      sender: 'Dr. John Matthews(your primary care physician)',
    },
    {
      title: 'Depression Screening',
      time: '2 week ago',
      sender: 'Dr. Nina Locke(Psychologist)',
    },
    {
      title: 'PHQ-9 ',
      time: '1 mon ago',
      sender: 'Dr. Jimmy',
    },
  ];

  return (
    <Card shadow="none">
      <CardHeader>
        <Heading size="s">Screenings and assessments</Heading>
      </CardHeader>
      <Listbox>
        {dataList.map((record, key) => {
          return (
            <Listbox.Item key={key}>
              <Icon name="assignment" size={20} appearance="primary" className="mr-4" />
              <div className="d-flex justify-content-between w-100 align-items-center">
                <div>
                  <div className="d-flex">
                    <Text>{record.title}</Text>
                    {record.status && (
                      <Badge appearance="alert" subtle={true} className="ml-4">
                        {record.status}
                      </Badge>
                    )}
                  </div>
                  <MetaList list={[{ label: `Sent by ${record.sender}` }, { label: `${record.time}` }]} />
                </div>
                <Icon name="chevron_right" size={20} appearance="subtle" />
              </div>
            </Listbox.Item>
          );
        })}
      </Listbox>
    </Card>
  );
}
```


#### Listbox

```jsx
import { Card, CardHeader, Heading, Listbox, Icon, Text, Badge, MetaList } from '@innovaccer/design-system';

() => {
  const dataList = [
    {
      title: 'Social Needs Assessment',
      time: '2 days ago',
      sender: 'Dr. John Matthews(your primary care physician)',
      status: 'Due',
    },
    {
      title: 'Diabetes Self Management Assessment',
      time: '1 week ago',
      sender: 'Dr. John Matthews(your primary care physician)',
    },
    {
      title: 'Depression Screening',
      time: '2 week ago',
      sender: 'Dr. Nina Locke(Psychologist)',
    },
    {
      title: 'PHQ-9 ',
      time: '1 mon ago',
      sender: 'Dr. Jimmy',
    },
  ];

  return (
    <Card shadow="none">
      <CardHeader>
        <Heading size="s">Screenings and assessments</Heading>
      </CardHeader>
      <Listbox size="tight">
        {dataList.map((record, key) => {
          return (
            <Listbox.Item key={key}>
              <Icon name="assignment" size={20} appearance="primary" className="mr-4" />
              <div className="d-flex justify-content-between w-100 align-items-center">
                <div>
                  <div className="d-flex">
                    <Text>{record.title}</Text>
                    {record.status && (
                      <Badge appearance="alert" subtle={true} className="ml-4">
                        {record.status}
                      </Badge>
                    )}
                  </div>
                  <MetaList list={[{ label: `Sent by ${record.sender}` }, { label: `${record.time}` }]} />
                </div>
                <Icon name="chevron_right" size={20} appearance="subtle" />
              </div>
            </Listbox.Item>
          );
        })}
      </Listbox>
    </Card>
  );
}
```


#### Listbox

```jsx
import { Card, CardHeader, Heading, Input, Text, Divider, CardBody, Listbox, Avatar, Button } from '@innovaccer/design-system';

() => {
  const dataList = [
    {
      firstName: 'John',
      lastName: 'Doe',
      email: 'john.doe@gmail.com',
      permission: 'Owner',
    },
    {
      firstName: 'Nina',
      lastName: 'Locke',
      email: 'ninalocke@gmail.com',
      permission: 'Can edit',
    },
    {
      firstName: 'Katty',
      lastName: 'Perry',
      email: 'kattyperry@gmail.com',
      permission: 'Can edit',
    },
    {
      firstName: 'Joy',
      lastName: 'Lawson',
      email: 'joylawson@gmail.com',
      permission: 'Can view',
    },
    {
      firstName: 'Randy',
      lastName: 'Boatwright',
      email: 'rboatwright3@arstechnica.com',
      permission: 'Can edit',
    },
    {
      firstName: 'Rolando',
      lastName: 'Cyples',
      email: 'rcyples4@biglobe.ne.jp',
      permission: 'Can edit',
    },
    {
      firstName: 'John',
      lastName: 'Doe',
      email: 'john.doe@gmail.com',
      permission: 'Owner',
    },
    {
      firstName: 'Nina',
      lastName: 'Locke',
      email: 'ninalocke@gmail.com',
      permission: 'Can edit',
    },
    {
      firstName: 'Katty',
      lastName: 'Perry',
      email: 'kattyperry@gmail.com',
      permission: 'Can edit',
    },
    {
      firstName: 'Joy',
      lastName: 'Lawson',
      email: 'joylawson@gmail.com',
      permission: 'Can view',
    },
    {
      firstName: 'Randy',
      lastName: 'Boatwright',
      email: 'rboatwright3@arstechnica.com',
      permission: 'Can edit',
    },
    {
      firstName: 'Rolando',
      lastName: 'Cyples',
      email: 'rcyples4@biglobe.ne.jp',
      permission: 'Can edit',
    },
  ];

  return (
    // style.css
    // .Listbox-wrapper {
    //   height: var(--spacing-9);
    // }
    <Card shadow="none">
      <CardHeader className="pb-4">
        <Heading size="s">Sharing test manual</Heading>
        <Input className=" mr-4 mt-5 w-25 mb-6" icon="search" name="input" placeholder="Search" />
        <Text size="medium">Showing 10 items</Text>
      </CardHeader>

      <Divider className="mt-3" appearance="header" />
      <CardBody className="p-0">
        <Listbox type="description" className="Listbox-wrapper overflow-auto">
          {dataList.map((data, key) => {
            return (
              <Listbox.Item key={key} id={key} disabled={key === 2} className="justify-content-between">
                <div className="d-flex align-items-center">
                  <Avatar firstName={data.firstName} lastName={data.lastName} />
                  <div className="ml-5">
                    <Text>{data.firstName + ' ' + data.lastName}</Text> <br />
                    <Text size="small" appearance="subtle">
                      {data.email}
                    </Text>
                  </div>
                </div>
                <Button
                  icon="keyboard_arrow_down"
                  iconAlign="right"
                  appearance="transparent"
                  onClick={(e) => e.stopPropagation()}
                >
                  {data.permission}
                </Button>
              </Listbox.Item>
            );
          })}
        </Listbox>
      </CardBody>
    </Card>
  );
}
```


#### Listbox

```jsx
import { Card, CardHeader, Heading, CardBody, Input, Dropdown, Tabs, Tab, Listbox, Text, StatusHint, CardFooter, Icon } from '@innovaccer/design-system';

() => {
  const dataList = [
    {
      name: 'ED Discharge care Protocol',
      subInfo: 'Pediatric',
      selected: true,
    },
    {
      name: 'Behavioral Outreach',
      subInfo: 'Remote patient monitoring',
      selected: false,
    },
    {
      name: 'Chronic Care Protocol - Diabetes',
      subInfo: 'Hospice',
      selected: false,
    },
    {
      name: 'TCM Care Protocol',
      subInfo: 'Chronic Care Management',
      selected: false,
    },
    {
      name: 'CAD Outreach',
      subInfo: 'Pharmacy management',
      selected: false,
    },
    {
      name: 'Diabetes care protocol',
      subInfo: 'Remote patient monitoring',
      selected: false,
    },
  ];
  return (
    // style.css
    // .Listbox-wrapper {
    //   height: var(--spacing-9);
    // }

    <Card shadow="none">
      <CardHeader>
        <Heading size="s">Select starting template</Heading>
      </CardHeader>
      <CardBody>
        <div className="d-flex w-50 mb-4">
          <Input className=" mr-4" icon="search" name="input" placeholder="Search" />
          <Dropdown
            options={[
              { label: 'Todo', value: 'TODO' },
              { label: 'In Progress', value: 'IN PROGRESS' },
              { label: 'Done', value: 'DONE' },
              { label: 'Closed', value: 'CLOSED' },
            ]}
            placeholder="Transition"
            withSearch={true}
          />
        </div>
        <Tabs activeIndex={0}>
          <Tab label="Suggested" count={6} className="Listbox-wrapper overflow-auto">
            <Listbox type="option">
              {dataList.map((data, key) => {
                return (
                  <Listbox.Item selected={data.selected} key={key} id={key} disabled={key === 2}>
                    <div className="d-flex w-100 justify-content-between">
                      <div>
                        <Text>{data.name}</Text>
                        <br />
                        <Text appearance="subtle">{data.subInfo}</Text>
                      </div>
                      <StatusHint appearance="info">{data.selected ? 'Selected' : 'Unselected'}</StatusHint>
                    </div>
                  </Listbox.Item>
                );
              })}
            </Listbox>
          </Tab>
          <Tab label="Your protocols" count={7} disabled={true}>
            <div>Your Protocol</div>
          </Tab>
        </Tabs>
      </CardBody>
      <CardFooter className="bg-light position-relative">
        <Icon name="add" size={20} appearance="primary" className="mr-3" />
        <Text appearance="link" weight="medium">
          Create from scratch
        </Text>
      </CardFooter>
    </Card>
  );
}
```


#### Listbox

```jsx
import { Card, CardHeader, Heading, Listbox, Icon, Text, Badge, MetaList, StatusHint } from '@innovaccer/design-system';

() => {
  const dataList = [
    {
      title: 'Social Needs Assessment',
      time: '2 days ago',
      sender: 'Dr. John Matthews(your primary care physician)',
      status: 'Due',
      activated: true,
    },
    {
      title: 'Diabetes Self Management Assessment',
      time: '1 week ago',
      sender: 'Dr. John Matthews(your primary care physician)',
      activated: false,
    },
    {
      title: 'Depression Screening',
      time: '2 week ago',
      sender: 'Dr. Nina Locke(Psychologist)',
      activated: false,
    },
    {
      title: 'PHQ-9 ',
      time: '1 mon ago',
      sender: 'Dr. Jimmy',
      activated: false,
    },
  ];

  return (
    <Card shadow="none">
      <CardHeader>
        <Heading size="s">Screenings and assessments</Heading>
      </CardHeader>

      <Listbox type="resource">
        {dataList.map((record, key) => {
          return (
            <Listbox.Item
              activated={record.activated}
              disabled={key === 2}
              id={key}
              key={key}
              className="justify-content-between"
            >
              <div className="d-flex align-items-center">
                <Icon name="assignment" size={20} appearance="primary" className="mr-4" />
                <div>
                  <div className="d-flex align-items-center">
                    <Text>{record.title}</Text>
                    {record.status && (
                      <Badge appearance="alert" subtle={true} className="ml-4">
                        {record.status}
                      </Badge>
                    )}
                  </div>
                  <MetaList list={[{ label: `Sent by ${record.sender}` }, { label: `${record.time}` }]} />
                </div>
              </div>
              <StatusHint appearance="info">{record.activated ? 'Active' : 'Inactive'}</StatusHint>
            </Listbox.Item>
          );
        })}
      </Listbox>
    </Card>
  );
}
```# Menu

Menu is used to display actions like navigation and page actions such as edit, export, delete, etc.

### Code Examples

#### Menu

```jsx
import { Menu } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        <Menu.Item>Edit</Menu.Item>
        <Menu.Item>Export</Menu.Item>
        <Menu.Item>Copy</Menu.Item>
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.Group>
        <Menu.List>
          <Menu.Item>Run Pipeline</Menu.Item>
        </Menu.List>
      </Menu.Group>

      <Menu.Group>
        <Menu.List>
          <Menu.Item>Logs</Menu.Item>
          <Menu.Item>Preview Data</Menu.Item>
          <Menu.Item>View Profile</Menu.Item>
        </Menu.List>
      </Menu.Group>

      <Menu.Group showDivider={false}>
        <Menu.List>
          <Menu.Item>Copy ID</Menu.Item>
          <Menu.Item>Delete</Menu.Item>
          <Menu.Item>Duplicate Pipeline</Menu.Item>
        </Menu.List>
      </Menu.Group>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.Group label="Add">
        <Menu.List>
          <Menu.Item>Add Product</Menu.Item>
          <Menu.Item>Add Custom</Menu.Item>
          <Menu.Item>Add Row</Menu.Item>
        </Menu.List>
      </Menu.Group>

      <Menu.Group label="Actions">
        <Menu.List>
          <Menu.Item>Edit</Menu.Item>
          <Menu.Item>Duplicate</Menu.Item>
          <Menu.Item>Share</Menu.Item>
        </Menu.List>
      </Menu.Group>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu, Icon } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.Group label="Group 1">
        <Menu.List>
          <Menu.Item>App store</Menu.Item>
          <Menu.Item>Developer Portal</Menu.Item>

          <Menu.SubMenu>
            <Menu.Item className="d-flex align-items-center justify-content-between w-100">
              User Admin
              <Icon name="chevron_right" />
            </Menu.Item>
            <Menu position="right-start">
              <Menu.List>
                <Menu.Item>Users</Menu.Item>
                <Menu.Item>Groups</Menu.Item>
                <Menu.Item>Roles</Menu.Item>
              </Menu.List>
            </Menu>
          </Menu.SubMenu>
        </Menu.List>
      </Menu.Group>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu, Text, Tooltip } from '@innovaccer/design-system';


() => {
  const [showTooltip, setShowTooltip] = React.useState(false);
  const elementRef = React.useRef(null);

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        <Menu.Item>
          <Text>Edit</Text>
        </Menu.Item>
        <Menu.Item>
          <Text>Export</Text>
        </Menu.Item>
        <Tooltip showOnTruncation={true} tooltip="Create a bug report here" open={showTooltip} elementRef={elementRef}>
          <Menu.Item onFocus={() => setShowTooltip(true)} onBlur={() => setShowTooltip(false)}>
            <Text ref={elementRef} className="ellipsis--noWrap">
              Create a bug report here
            </Text>
          </Menu.Item>
        </Tooltip>
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu, Text, Tooltip, Icon } from '@innovaccer/design-system';


() => {

  /*
    .SubMenu-Text {
      width: var(--spacing-7);
    }
  */
  const [showTooltip, setShowTooltip] = React.useState(false);
  const elementRef = React.useRef(null);

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        <Menu.Item>
          <Text>Edit</Text>
        </Menu.Item>
        <Menu.Item>
          <Text>Export</Text>
        </Menu.Item>
        <Menu.SubMenu>
          <Menu.Item
            onFocus={() => {
              setShowTooltip(true);
            }}
            onBlur={() => {
              setShowTooltip(false);
            }}
          >
            <Tooltip showOnTruncation={true} tooltip="User Admin Settings" open={showTooltip} elementRef={elementRef}>
              <div className="justify-space-between d-flex align-items-center w-100">
                <Text ref={elementRef} className="ellipsis--noWrap SubMenu-Text">
                  User Admin Settings
                </Text>
                <Icon name="chevron_right" />
              </div>
            </Tooltip>
          </Menu.Item>
          <Menu position="right-start">
            <Menu.List>
              <Menu.Item>Users</Menu.Item>
              <Menu.Item>Groups</Menu.Item>
              <Menu.Item>Roles</Menu.Item>
            </Menu.List>
          </Menu>
        </Menu.SubMenu>
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Row, Column, Label, Menu } from '@innovaccer/design-system';


() => {

  return (
    <Row>
      <Column>
        <Label withInput={true}>Compressed Options</Label>
        <br />
        <Menu trigger={<Menu.Trigger />}>
          <Menu.List size="compressed">
            <Menu.Item>Edit</Menu.Item>
            <Menu.Item>Export</Menu.Item>
            <Menu.Item>Copy</Menu.Item>
          </Menu.List>
        </Menu>
      </Column>

      <Column>
        <Label withInput={true}>Standard Options</Label>
        <br />
        <Menu trigger={<Menu.Trigger />}>
          <Menu.List size="standard">
            <Menu.Item>Edit</Menu.Item>
            <Menu.Item>Export</Menu.Item>
            <Menu.Item>Copy</Menu.Item>
          </Menu.List>
        </Menu>
      </Column>

      <Column>
        <Label withInput={true}>Tight Options</Label>
        <br />
        <Menu trigger={<Menu.Trigger />}>
          <Menu.List size="tight">
            <Menu.Item>Edit</Menu.Item>
            <Menu.Item>Export</Menu.Item>
            <Menu.Item>Copy</Menu.Item>
          </Menu.List>
        </Menu>
      </Column>
    </Row>
  );
}

```


#### Menu

```jsx
import { Row, Column, Label, Menu } from '@innovaccer/design-system';


() => {

  return (
    <Row>
      <Column>
        <Label withInput={true}>Tiny</Label>
        <br />
        <Menu trigger={<Menu.Trigger size="tiny" />}>
          <Menu.List>
            <Menu.Item>Edit</Menu.Item>
            <Menu.Item>Export</Menu.Item>
            <Menu.Item>Copy</Menu.Item>
          </Menu.List>
        </Menu>
      </Column>

      <Column>
        <Label withInput={true}>Regular</Label>
        <br />
        <Menu trigger={<Menu.Trigger size="regular" />}>
          <Menu.List>
            <Menu.Item>Edit</Menu.Item>
            <Menu.Item>Export</Menu.Item>
            <Menu.Item>Copy</Menu.Item>
          </Menu.List>
        </Menu>
      </Column>
    </Row>
  );
}

```


#### Menu

```jsx
import { Menu, Button } from '@innovaccer/design-system';


() => {

  return (
    <Menu
      trigger={
        <Button icon="expand_more" iconAlign="right">
          Page actions
        </Button>
      }
    >
      <Menu.List>
        <Menu.Item>Edit</Menu.Item>
        <Menu.Item>Export</Menu.Item>
        <Menu.Item>Copy</Menu.Item>
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        <Menu.Item>Edit</Menu.Item>
        <Menu.Item>Export</Menu.Item>
        <Menu.Item>Copy</Menu.Item>
      </Menu.List>
    </Menu>
  );
}

```


#### Components Menu Trigger Right Click

```jsx
import { Text, Menu } from '@innovaccer/design-system';

() => {

  const [popoverVisible, setPopoverVisible] = React.useState(false);
  const [popoverPosition, setPopoverPosition] = React.useState({ x: 0, y: 0 });

  const handleContextMenu = (event) => {
    event.preventDefault();
    
    const x = event.clientX;
    const y = event.clientY;
    
    setPopoverPosition({ x, y });
    setPopoverVisible(true);
  };

  const handleDocumentClick = () => {
    setPopoverVisible(false);
  };

  return ( 
    <div className="bg-secondary-lighter p-10" onContextMenu={handleContextMenu} onClick={handleDocumentClick}>
      <Text>Right click to open popover</Text>
      <Menu triggerCoordinates={popoverPosition} open={popoverVisible}>
        <Menu.List>
          <Menu.Item>Edit</Menu.Item>
          <Menu.Item>Export</Menu.Item>
          <Menu.Item>Copy</Menu.Item>
        </Menu.List>
      </Menu>
    </div> 
  );
}

```


#### Menu

```jsx
import { Menu, Icon } from '@innovaccer/design-system';


() => {
  const [itemList, setItemList] = React.useState([]);
  const actionList = ['Edit', 'Export', 'Copy'];

  const onClickHandler = (action) => {
    if (itemList.includes(action)) {
      const list = itemList.filter((item) => item !== action);
      setItemList(list);
    } else {
      setItemList([...itemList, action]);
    }
  };

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        {actionList.map((actions) => {
          return (
            <Menu.Item key={actions} onClick={() => onClickHandler(actions)} className="d-flex justify-content-between">
              {actions}
              {itemList.includes(actions) && <Icon name="done" />}
            </Menu.Item>
          );
        })}
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu, Icon, Text } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        <Menu.Item className="d-flex align-items-center">
          <Icon name="edit" className="mr-4 my-2" />
          <Text>Edit</Text>
        </Menu.Item>
        <Menu.Item className="d-flex align-items-center">
          <Icon name="content_Copy" className="mr-4 my-2" />
          <Text>Copy</Text>
        </Menu.Item>
        <Menu.Item className="d-flex align-items-center">
          <Icon name="share" className="mr-4 my-2" />
          <Text>Share</Text>
        </Menu.Item>
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu, Text } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        <Menu.Item className="d-flex align-items-center justify-content-between">
          <Text>Run</Text>
          <Text appearance="subtle">Cmd + R</Text>
        </Menu.Item>
        <Menu.Item className="d-flex align-items-center justify-content-between">
          <Text>Preview</Text>
          <Text appearance="subtle">Cmd + P</Text>
        </Menu.Item>
        <Menu.Item className="d-flex align-items-center justify-content-between">
          <Text>Copy</Text>
          <Text appearance="subtle">Cmd + C</Text>
        </Menu.Item>
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu, Text } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        <Menu.Item className="d-flex flex-column align-items-start">
          <Text>Edit</Text>
          <Text appearance="subtle" size="small" weight="medium">
            Changes will be saved
          </Text>
        </Menu.Item>
        <Menu.Item>
          <Text>Copy</Text>
        </Menu.Item>
        <Menu.Item>
          <Text>Share</Text>
        </Menu.Item>
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu, Icon, Text } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        <Menu.Item className="d-flex align-items-center">
          <Icon name="edit" className="mr-4 my-2" />
          <Text>Edit</Text>
        </Menu.Item>
        <Menu.Item className="d-flex align-items-center">
          <Icon name="content_Copy" className="mr-4 my-2" />
          <Text>Copy</Text>
        </Menu.Item>
        <Menu.Item className="d-flex align-items-center">
          <Icon name="delete" appearance="alert" className="mr-4 my-2" type="rounded" />
          <Text appearance="destructive">Delete</Text>
        </Menu.Item>
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu, Text } from '@innovaccer/design-system';


() => {

  return (
    <Menu trigger={<Menu.Trigger />}>
      <Menu.List>
        <Menu.Item className="d-flex flex-column align-items-start">
          <Text appearance="destructive">Delete</Text>
          <Text appearance="subtle" size="small" weight="medium">
            Changes will be lost.
          </Text>
        </Menu.Item>
        <Menu.Item>
          <Text>Copy</Text>
        </Menu.Item>
        <Menu.Item>
          <Text>Share</Text>
        </Menu.Item>
      </Menu.List>
    </Menu>
  );
}

```


#### Menu

```jsx
import { Menu, Text } from '@innovaccer/design-system';


() => {

  return (
    <div className="d-flex justify-content-between">
      <Menu trigger={<Menu.Trigger />}>
        <Menu.List>
          <Menu.Item>
            <Text>Edit</Text>
          </Menu.Item>
          <Menu.Item>
            <Text>Export</Text>
          </Menu.Item>
          <Menu.Item>
            <Text>Copy</Text>
          </Menu.Item>
        </Menu.List>
      </Menu>

      <Menu trigger={<Menu.Trigger />}>
        <Menu.List>
          <Menu.Item>
            <Text>Edit</Text>
          </Menu.Item>
          <Menu.Item>
            <Text>Export</Text>
          </Menu.Item>
          <Menu.Item>
            <Text appearance="destructive">Delete</Text>
          </Menu.Item>
        </Menu.List>
      </Menu>
    </div>
  );
}

```


#### Menu

```jsx
import { Menu, Icon, Text } from '@innovaccer/design-system';


() => {

  return (
<div className="d-flex justify-content-between">
      <Menu trigger={<Menu.Trigger />}>
        <Menu.List>
          <Menu.Item className="d-flex align-items-center">
            <Icon name="edit" className="mr-4 my-2" />
            <Text>Edit</Text>
          </Menu.Item>
          <Menu.Item className="d-flex align-items-center">
            <Icon name="content_Copy" className="mr-4 my-2" />
            <Text>Copy</Text>
          </Menu.Item>
          <Menu.Item className="d-flex align-items-center">
            <Icon name="share" className="mr-4 my-2" />
            <Text>Share</Text>
          </Menu.Item>
        </Menu.List>
      </Menu>

      <Menu trigger={<Menu.Trigger />}>
        <Menu.List>
          <Menu.Item className="d-flex align-items-center">
            <Icon name="edit" className="mr-4 my-2" />
            <Text>Edit</Text>
          </Menu.Item>
          <Menu.Item className="d-flex align-items-center">
            <Icon name="content_Copy" className="mr-4 my-2" />
            <Text>Copy</Text>
          </Menu.Item>
          <Menu.Item className="d-flex align-items-center">
            <Icon name="delete" appearance="alert" className="mr-4 my-2" type="rounded" />
            <Text appearance="destructive">Delete</Text>
          </Menu.Item>
        </Menu.List>
      </Menu>
    </div>
  );
}

```


#### Menu

```jsx
import { Menu, Text } from '@innovaccer/design-system';


() => {

  return (
    <div className="d-flex justify-content-between">
      <Menu trigger={<Menu.Trigger />}>
        <Menu.List>
          <Menu.Item className="d-flex flex-column align-items-start">
            <Text>Edit</Text>
            <Text appearance="subtle" size="small" weight="medium">
              Changes will be saved
            </Text>
          </Menu.Item>
          <Menu.Item>
            <Text>Copy</Text>
          </Menu.Item>
          <Menu.Item>
            <Text>Share</Text>
          </Menu.Item>
        </Menu.List>
      </Menu>

      <Menu trigger={<Menu.Trigger />}>
        <Menu.List>
          <Menu.Item className="d-flex flex-column align-items-start">
            <Text appearance="destructive">Delete</Text>
            <Text appearance="subtle" size="small" weight="medium">
              Changes will be lost.
            </Text>
          </Menu.Item>
          <Menu.Item>
            <Text>Copy</Text>
          </Menu.Item>
          <Menu.Item>
            <Text>Share</Text>
          </Menu.Item>
        </Menu.List>
      </Menu>
    </div>
  );
}

```# Message

Messages are used to display important information and provide relevant actions for users to address. The information can be specific to a page, section or field.

### Code Examples

#### Components Message All

```jsx
import { Message, LinkButton } from '@innovaccer/design-system';

() => {
  const title = 'Design System';
  const description = 'Design System is a library of reusable components';

  return (
    <Message
      title={title}
      description={description}
      actions={
        <>
          <LinkButton>Action 1</LinkButton>
          <LinkButton className="ml-5">Action 2</LinkButton>
        </>
      }
    />
  );
}
```


#### Components Message Appearance Alert

```jsx
import { Message } from '@innovaccer/design-system';

() => (
  <Message className="w-50" appearance="alert" description="Could not start verification. Please try again later." />
)
```


#### Components Message Appearance Info

```jsx
import { Message } from '@innovaccer/design-system';

() => (
  <Message className="w-50" appearance="info" description="Patient profile has been updated with new records." />
)
```


#### Components Message Appearance Success

```jsx
import { Message } from '@innovaccer/design-system';

() => (
  <Message className="w-50" appearance="success" description="Password updated. Login with your updated credentials." />
)
```


#### Components Message Appearance Warning

```jsx
import { Message } from '@innovaccer/design-system';

() => (
  <Message
    className="w-50"
    appearance="warning"
    description="Try to save again. If it continues to fail, please raise a ticket."
  />
)
```


#### Components Message Custom Description

```jsx
import { Message, LinkButton, Text } from '@innovaccer/design-system';

() => (
  <Message className="w-75" actions={<LinkButton>Try again</LinkButton>}>
    <Text>Sorry we couldn't subscribe you. Please try again.</Text>
  </Message>
)
```


#### Components Message Message With Actions

```jsx
import { Message, LinkButton } from '@innovaccer/design-system';

() => (
  <Message
    className="w-50"
    appearance="alert"
    description="Sorry we couldn't subscribe you. Please try again."
    actions={<LinkButton>Try again</LinkButton>}
  />
)
```


#### Components Message Message With Title

```jsx
import { Message, LinkButton } from '@innovaccer/design-system';

() => (
  <Message
    className="w-50"
    appearance="warning"
    title="Sender 'Alta Wells' already exists "
    description="Based on the details you've entered, we found that this sender might already be on our platform."
    actions={<LinkButton>Edit details</LinkButton>}
  />
)
```


#### Message

```jsx
import { Text, Message, LinkButton } from '@innovaccer/design-system';

() => {
  const appearances = ['alert', 'info', 'success', 'warning'];
  return (
    <div>
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="mb-7">
            <Text weight="strong">{appear.charAt(0).toUpperCase() + appear.slice(1)}</Text>
            <Message
              actions={
                <>
                  <LinkButton>Action 1</LinkButton>
                  <LinkButton className="ml-5">Action 2</LinkButton>
                </>
              }
              className="mt-4"
              appearance={appear}
              title="Outreach was not saved"
              description="Patient record has been updated with new records."
            />
          </div>
        );
      })}
    </div>
  );
}
```


#### Message

```jsx
import { Text, Message, LinkButton } from '@innovaccer/design-system';

() => {
  const appearances = ['alert', 'info', 'success', 'warning'];
  return (
    <div>
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="mb-7">
            <Text weight="strong">{appear.charAt(0).toUpperCase() + appear.slice(1)}</Text>
            <Message
              actions={
                <>
                  <LinkButton>Action 1</LinkButton>
                  <LinkButton className="ml-5">Action 2</LinkButton>
                </>
              }
              className="mt-4"
              appearance={appear}
              description="Patient record has been updated with new records."
            />
          </div>
        );
      })}
    </div>
  );
}
```# MetaList

Meta list is a short horizontal list of meta/secondary information.

### Code Examples

#### MetaList

```jsx
import { MetaList } from '@innovaccer/design-system';

() => {
  const list = [
    {
      label: 'Meta data',
      icon: 'assessment',
    },
    {
      label: 'Meta data',
      icon: 'assessment',
    },
  ];

  return <MetaList list={list} />;
}
```


#### MetaList

```jsx
import { Text, MetaList } from '@innovaccer/design-system';

() => {
  const list = [
    {
      label: 'Meta data',
      icon: 'assessment',
    },
    {
      label: 'Meta data',
      icon: 'assessment',
    },
  ];

  return (
    <div className="ml-5">
      <Text weight="strong">Small</Text>
      <MetaList className="py-7" list={list} seperator={true} size="small" />

      <Text weight="strong">Regular</Text>
      <MetaList className="py-7" list={list} seperator={true} />
    </div>
  );
}
```


#### MetaList

```jsx
import { MetaList } from '@innovaccer/design-system';

() => {
  const seperator = true;

  const list = [
    {
      label: 'Meta data',
      icon: 'assessment',
    },
    {
      label: 'Meta data',
      icon: 'assessment',
    },
  ];

  return <MetaList list={list} seperator={seperator} />;
}
```# MetricInput



### Code Examples

#### Input

```jsx
import { MetricInput } from '@innovaccer/design-system';

() => {
  const size = 'regular';

  const placeholder = 'Placeholder';

  const disabled = false;

  const readOnly = false;

  const icon = '';

  const prefix = '';

  const suffix = '';

  const error = false;

  return (
    <div className="w-25">
      <MetricInput
        name="input"
        disabled={disabled}
        readOnly={readOnly}
        onChange={action('on-change')}
        onClick={action('on-click')}
        placeholder={placeholder}
        aria-label="Metric input example"
        prefix={prefix}
        suffix={suffix}
        size={size}
        icon={icon}
        error={error}
      />
    </div>
  );
}
```


#### Input

```jsx
import { Row, Column, MetricInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(10);

  return (
    <Row>
      <Column size={1}>
        <MetricInput
          aria-label="Metric Input Label"
          value={value}
          onChange={(e) => { setValue(e.target.value) }}
        />
      </Column>
    </Row>
  );
}
```


#### Input

```jsx
import { Row, Label, Column, MetricInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(15);

  return (
    <Row className="align-items-center">
      <Label htmlFor="metric-input" className="mr-5">  No. of Days </Label>
      <Column size={1}>
        <MetricInput
          id="metric-input"
          name="metric-input"
          size="regular"
          value={value}
          onChange={e => { setValue(e.target.value); }}
        />
        </Column>
    </Row>
  );
}
```


#### Input

```jsx
import { Row, Label, Column, MetricInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(2000);

  const onKeyDownHandler = (e) => {
    if (/[.]/.test(e.key)) {
      e.preventDefault();
    }
  };

  const isInteger = (val) => {
    return val - Math.floor(val) === 0 ? true : false;
  };

  return (
    <Row className="align-items-center">
      <Label htmlFor="metric-input" className="mr-5">
        Year
      </Label>
      <Column size={2}>
        <MetricInput
          id="metric-input"
          value={isInteger(value) ? value : 0}
          onChange={(e) => {
            setValue(e.target.value);
          }}
          onKeyDown={onKeyDownHandler}
        />
      </Column>
    </Row>
  );
}
```


#### Input

```jsx
import { Row, Column, MetricInput, Text } from '@innovaccer/design-system';

() => (
  <Row>
    <Column size={2} className="d-flex">
      <div className="flex-column align-items-center mr-8">
        <MetricInput aria-label="Metric input regular size" size="regular" className="mb-3" />
        <Text>Regular</Text>
      </div>
      <div className="flex-column align-items-center">
        <MetricInput aria-label="Metric input large size" size="large" className="mb-3" />
        <Text>Large</Text>
      </div>
    </Column>
  </Row>
)
```


#### Input

```jsx
import { Row, Label, Column, MetricInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(625);

  return (
    <Row className="align-items-center">
      <Label htmlFor="metric-input" className="mr-5">Cost</Label>
      <Column size={2}>
        <MetricInput
          id="metric-input"
          prefix="USD"
          value={value}
          onChange={e => { setValue(e.target.value); }}
        />
      </Column>
    </Row>
  );
}
```


#### Input

```jsx
import { Row, Label, Column, MetricInput } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(65);

  return (
    <Row className="align-items-center">
      <Label htmlFor="metric-input" className="mr-5">Body Height</Label>
      <Column size={2}>
        <MetricInput
          id="metric-input"
          suffix="in"
          value={value}
          onChange={e => { setValue(e.target.value); }}
        />
      </Column>
    </Row>
  );
}
```# Modal



### Code Examples

#### Modal

```jsx
import { Button, Modal, Text, ModalDescription } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const dimension = 'medium';
  const backdropClose = true;

  const onClose = () => {
    setOpen(!open);
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Heading',
          subHeading: 'Subheading'
        }}
        footer={(
          <>
            <Button appearance="basic" onClick={()=>console.log('Basic button click')}>Basic</Button>
            <Button appearance="primary" className="ml-4" onClick={()=>console.log('Primary button click')}>Primary</Button>
          </>
        )}
      >
        <Text>Modal Body</Text>
        <ModalDescription
          title="Description Title"
          description="Adding a subheading clearly indicates the hierarchy of the information."
        />
        <ModalDescription
          description="Card Sections include supporting text like an article summary or a healthcare service description."
        />
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Button, Modal, Paragraph } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const backdropClose = false;
  const dimension = 'small';

  const onClose = () => {
    setOpen(!open);
    console.log('on close triggered');
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Discard Changes',
        }}
        footer={(
          <>
            <Button appearance="basic" onClick={console.log('Cancel button click')}>Cancel</Button>
            <Button appearance="alert" className="ml-4" onClick={console.log('Discard button click')}>Discard</Button>
          </>
        )}
      >
        <Paragraph>
            You are about to discard all the saved filters.
            Once discarded, this action cannot be undone.
            Please be sure of it.
        </Paragraph>
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Button, Modal, Paragraph, Text } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const backdropClose = false;
  const dimension = 'medium';

  const onClose = () => {
    setOpen(!open);
    console.log('on close triggered');
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Edit filters',
        }}
        footer={(
          <>
            <Button appearance="basic" onClick={console.log('Cancel button click')}>Cancel</Button>
            <Button appearance="primary" className="ml-4" onClick={console.log('Discard button click')}>
                Create version
            </Button>
          </>
        )}
      >
        <Paragraph>
          Currently, Version 1.0 is published.
          This will create a new version of the registry which will be saved as draft untill published.<br />
        </Paragraph><br/>
        <Text>Do you want to continue?</Text>
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Text, Button, Modal, Message, List } from '@innovaccer/design-system';

/*
// styles.css
.Modal-list {
    height: var(--spacing-8);
}
*/

() => {
  const [open, setOpen] = React.useState(false);
  const backdropClose = true;
  const dimension = 'medium';
  const onClose = () => {
    setOpen(!open);
    console.log('on close triggered');
  };

  const data = [{ Name:'ER Education' }, { Name:'HbA1c Test Due' } , { Name:'Flu Vaccination' }  , { Name:'Well-Child Visit' }, { Name:'Cervical Screening' }, { Name:'HbA1c Test Due' } , { Name:'Flu Vaccination' }  , { Name:'Well-Child Visit' }, { Name:'Cervical Screening' }, { Name:'HbA1c Test Due' } , { Name:'Flu Vaccination' }  , { Name:'Well-Child Visit' }];

  const schema = [
    {
      name: 'info',
      displayName: 'Info',
      cellRenderer: (props) => {
        return (
          <Text className=" ml-4">{`${props.data.Name}`}</Text>
        );
      }
    },
  ];

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Cannot delete Leona Lucas',
        }}
        footer={(
          <>
            <Button className="ml-4" onClick={console.log('Close button click')}>Close</Button>
          </>
        )}
      >
        <div>
          <Message
            appearance="warning"
            description="Following 11 outreaches are currently scheduled using this sender's details."
          />
        </div>
        <div className="my-5 overflow-auto border Modal-list">
          <List
            data={data}
            schema={schema}
            size="compressed"
          />
        </div>
        <Text weight="strong" className="mt-2">What to do next?</Text><br/>
        <Text>
          You cannot delete this sender until the scheduled outreaches have been completed or cancelled.
        </Text>
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Navigation, Heading, Button, Modal, Label, Select } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const backdropClose =false;

  const onClose = () => {
    setOpen(!open);
    console.log('on close triggered');
  };

  const options = [
    {
      label: 'Option1',
      value: 'Option1',
    },
    {
      label: 'Option2',
      value: 'Option2',
    }
  ];

  const data = [
    {
      label: 'Medicine',
      name: 'Tab1'
    },
    {
      label: 'Period',
      name: 'Tab2'
    },
    {
      label: 'Alias',
      name: 'Tab3'
    },
    {
      label: 'Priority',
      name: 'Tab4'
    }
  ];

  const [active, setActive] = React.useState({
    name: 'Tab1'
  });

  const onClickHandler = (menu) => {
    setActive(menu);
  };

  const subHeading = (
    <Navigation
      align="left"
      menus={data}
      active={active}
      onClick={onClickHandler}
      className="ml-5 mt-4"
    />
  );

  const header = (
    <div>
      <Heading className="ml-7 mb-3">Medication</Heading>
      {subHeading}
    </div>
  );

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension="large"
        backdropClose={backdropClose}
        onClose={onClose}
        header={header}
        footer={(
          <>
            <Button appearance="basic" onClick={console.log('Cancel button click')}>Discard</Button>
            <Button appearance="primary" className="ml-4" onClick={console.log('Discard button click')}>
                Create operand
            </Button>
          </>
        )}
      >
        <div className="my-5">
          <Label withInput={true} required={true}>Type</Label>
          <Select triggerOptions={{ withClearButton: false }}>
            <Select.List>
              {options.map((item, key) => {
                return (
                  <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                    {item.label}
                  </Select.Option>
                );
              })}
            </Select.List>
          </Select>
          <Label withInput={true} className="mt-5">Active Date</Label>
          <Select triggerOptions={{ withClearButton: false }}>
            <Select.List>
              {options.map((item, key) => {
                return (
                  <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                    {item.label}
                  </Select.Option>
                );
              })}
            </Select.List>
          </Select>
          <div className="d-flex pb-4">
            <div className="d-block w-75">
              <Label withInput={true} required={true} className="mt-5">Diagnosis Diseases</Label>
              <Select triggerOptions={{ withClearButton: false }} width="100%">
                <Select.List>
                  {options.map((item, key) => {
                    return (
                      <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                        {item.label}
                      </Select.Option>
                    );
                  })}
                </Select.List>
              </Select>
            </div>
            <div className="ml-5 d-block w-25">
              <Label withInput={true} required={true} className="mt-5">Version</Label>
              <Select triggerOptions={{ withClearButton: false }} width="100%">
                <Select.List>
                  {options.map((item, key) => {
                    return (
                      <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                        {item.label}
                      </Select.Option>
                    );
                  })}
                </Select.List>
              </Select>
            </div>
          </div>
        </div>
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Button, Modal, Text, ModalDescription } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const [openSecondOverlay, setOpenSecondOverlay] = React.useState(false);
  const dimension = 'medium';
  const backdropClose = true;

  const onClose = () => {
    setOpen(!open);
  };

  const onCloseSecondOverlay = () => {
    setOpenSecondOverlay(!openSecondOverlay);
  }

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        closeOnEscape={true}
        open={open}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Heading',
          subHeading: 'Subheading'
        }}
        footer={(
          <>
            <Button appearance="basic" onClick={()=>console.log('Basic button click')}>Basic</Button>
            <Button appearance="primary" className="ml-4" onClick={()=> setOpenSecondOverlay(true)}>Open</Button>
          </>
        )}
      >
        <Text>Modal Body</Text>
        <ModalDescription
          title="Description Title"
          description="Adding a subheading clearly indicates the hierarchy of the information."
        />
        <ModalDescription
          description="Card Sections include supporting text like an article summary or a healthcare service description."
        />
      </Modal>

      <Modal
        closeOnEscape={true}
        open={openSecondOverlay}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onCloseSecondOverlay}
        headerOptions={{
          heading: 'Heading Part Two',
          subHeading: 'Subheading Part Two',
        }}
        footer={
          <>
            <Button appearance="primary" className="ml-4" onClick={() => console.log('Primary button click')}>
              Primary
            </Button>
          </>
        }
      >
        <Text>Modal Part Two Body</Text>
        <ModalDescription description="Card Sections include supporting text like an article summary or a healthcare service description." />
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Button, Modal, Text, ModalDescription } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const dimension = 'medium';
  const backdropClose = true;

  const onClose = () => {
    setOpen(!open);
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Heading',
          subHeading: 'Subheading'
        }}
      >
        <Text>Modal Body</Text>
        <ModalDescription
          title="Description Title"
          description="Adding a subheading clearly indicates the hierarchy of the information."
        />
        <ModalDescription
          description="Card Sections include supporting text like an article summary or a healthcare service description."
        />
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Button, Modal, ModalHeader, ModalBody, Text, ModalDescription, ModalFooter } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const dimension = 'medium';

  const onClose = () => {
    setOpen(!open);
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension={dimension}
        backdropClose={onClose}
      >
        <ModalHeader
          onClose={onClose}
          heading="Heading"
          subHeading="Subheading"
        />
        <ModalBody>
          <Text>Modal Body</Text>
          <ModalDescription
            title="Description Title"
            description="Adding a subheading clearly indicates the hierarchy of the information."
          />
          <ModalDescription
            description="Card Sections include supporting text like an article summary or a healthcare service description."
          />
        </ModalBody>
        <ModalFooter open={open}>
          <Button appearance="basic" onClick={()=>console.log('Basic button click')}>Basic</Button>
          <Button appearance="primary" className="ml-4" onClick={()=>console.log('Primary button click')}>Primary</Button>
        </ModalFooter>
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Button, Modal, Text, Chip } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const backdropClose = false;

  const onClose = () => {
    setOpen(!open);
    console.log('on close triggered');
  };

  const data = [{"question":"Do you experience any of the following in your current place of residence? [Select all that apply]", "options":["Deteriorating appearance","Inoperable plumbing","Inadequate wining","Leaking roofs","Crumbling foundations","Unsafe steps","in poor condition","None of the above"]},
    {"question":"In last 12 months, were you worried that your food would run out before you got money to buy more?", "options":["Yes","No"]},
    {"question":"Moving or speaking so slowly that other people could have noticed? Or the opposite - being so fidgety or restless that you have been moving around a lot more than usual", "options":["Not at all","Several Days","More than half the days","Nearly every day"]},
    {"question":"Feeling tired or having little energy?", "options":["Yes","No"]},
    {"question": "Which of the following refers to a programme that aims to enable patients to make better use of information and communication technology for health and health care?", "options":["patient informatics","ICT health","Health-tech","None of these"]},
    {"question": "The way messages are framed influences people’s intentions and willingness to change their behaviour. Which of the following refers to the type of message framing that gives information about a health behaviour that emphasizes the costs of failing to take action?", "options":["Gain-framed messages","Loss-framed messages","Neutrally-framed messages","None of these"]},
    {"question": "Which of the following refers to the capacity to access, understand, appraise and apply health information and services, and to make appropriate health decisions to promote and maintain health?", "options":["health accessibility","health appraisal","health literacy","health promotion"]},
    {"question": "Frederich Engels’ book entitled The Condition of the Working Class in England in 1844 provided a detailed description of the appalling living and working conditions and the limited health care of working-class residents in which of the following English cities?", "options":["London","Manchester","Liverpool","None of these"]},
    {"question": "Which of the following explanations for health inequalities focus on the individual as the unit of analysis, emphasizing unthinking, reckless or irresponsible behaviour or incautious lifestyle as the moving determinant?", "options":["Individualist explanations","Natural and social selection","Materialist and structuralist explanations","Cultural and/or behavioural differences"]},
    {"question": "This approach to health promotion is based on the assumption that humans are rational decision-makers, this approach relies heavily upon the provision of information about risks and benefits of certain behaviours.", "options":["Behaviour change approach","Community development approach","Biomedical approach","None of these"]},
  ];

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension="large"
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Survey',
        }}
        footer={(
          <>
            <Button  onClick={() => console.log('Cancel button click')}>Cancel</Button>
            <Button appearance="primary" className="ml-4" onClick={() => console.log('Next button click')}>Next</Button>
          </>
        )}
        seperator={true}
      >
        <div className="mt-5">
          <Text weight="strong">All questions must be answered, unless marked</Text><br/>
          {
            data.map((object, index) => {
              return(
                <div key={index} className="mt-5 d-flex">
                  <div >
                    <Text size="regular" className="mr-4">
                    {`${index + 1}.`}
                    </Text>
                  </div>
                  <div className="d-inline-block ml-2">
                    <Text size="regular">
                      {object.question}
                    </Text>
                    <div className="mb-5 mt-3">
                      {
                        object.options.map((option , ind) => {
                          return <Chip key={ind} type="selection" label={option} className="mr-4 mt-4"/>;
                        })
                      }
                    </div>
                  </div>
                </div>
              );
            })
          }
        </div>
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Button, Modal, Text, ModalDescription } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const dimension = 'large';
  const backdropClose = true;

  const onClose = () => {
    setOpen(!open);
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Heading',
          subHeading: 'Subheading'
        }}
        footer={(
          <>
            <Button appearance="basic" onClick={()=>console.log('Basic button click')}>Basic</Button>
            <Button appearance="primary" className="ml-4" onClick={()=>console.log('Primary button click')}>Primary</Button>
          </>
        )}
      >
        <Text>Modal Body</Text>
        <ModalDescription
          title="Description Title"
          description="Adding a subheading clearly indicates the hierarchy of the information."
        />
        <ModalDescription
          description="Card Sections include supporting text like an article summary or a healthcare service description."
        />
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Button, Modal, Text, ModalDescription } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const dimension = 'medium';
  const backdropClose = true;

  const onClose = () => {
    setOpen(!open);
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Heading',
          subHeading: 'Subheading'
        }}
        footer={(
          <>
            <Button appearance="basic" onClick={()=>console.log('Basic button click')}>Basic</Button>
            <Button appearance="primary" className="ml-4" onClick={()=>console.log('Primary button click')}>Primary</Button>
          </>
        )}
      >
        <Text>Modal Body</Text>
        <ModalDescription
          title="Description Title"
          description="Adding a subheading clearly indicates the hierarchy of the information."
        />
        <ModalDescription
          description="Card Sections include supporting text like an article summary or a healthcare service description."
        />
      </Modal>
    </div>
  );
}
```


#### Modal

```jsx
import { Button, Modal, Text, ModalDescription } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const dimension = 'small';
  const backdropClose = true;

  const onClose = () => {
    setOpen(!open);
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>Open Modal</Button>
      <Modal
        open={open}
        dimension={dimension}
        backdropClose={backdropClose}
        onClose={onClose}
        headerOptions={{
          heading: 'Heading',
          subHeading: 'Subheading'
        }}
        footer={(
          <>
            <Button appearance="basic" onClick={()=>console.log('Basic button click')}>Basic</Button>
            <Button appearance="primary" className="ml-4" onClick={()=>console.log('Primary button click')}>Primary</Button>
          </>
        )}
      >
        <Text>Modal Body</Text>
        <ModalDescription
          title="Description Title"
          description="Adding a subheading clearly indicates the hierarchy of the information."
        />
        <ModalDescription
          description="Card Sections include supporting text like an article summary or a healthcare service description."
        />
      </Modal>
    </div>
  );
}
```# Navigation



### Code Examples

#### Navigation

```jsx
import {  } from '@innovaccer/design-system';

() => <></>
```# OutsideClick



### Code Examples

#### Components Utilities OutsideClick All

```jsx
import { OutsideClick, Card, Heading } from '@innovaccer/design-system';

() => {
  const outsideClickHandler = () => console.log('outside click');
  const insideClickHandler = () => console.log('inside click');

  return(
    <OutsideClick className="d-inline-block" onOutsideClick={outsideClickHandler}>
      <Card
        className="d-flex align-items-center justify-content-center p-10"
        onClick={insideClickHandler}
      >
        <Heading>Card</Heading>
      </Card>
    </OutsideClick>
  );
}
```# PageHeader



### Code Examples

#### Components PageHeader Level 0 With Navigation

```jsx
import { HorizontalNav, Button, Row, Column, PageHeader } from '@innovaccer/design-system';

() => {
  const navigationData = [
    {
      name: 'menu_1',
      label: 'Virtual Visits',
    },
    {
      name: 'menu_2',
      label: 'Assesments'
    }
  ];

  const [active, setActive] = React.useState({
    name: 'menu_1'
  });

  const onClickHandler = (menu) => {
    setActive(menu);
  };

  const navigation = <HorizontalNav menus={navigationData} onClick={onClickHandler} active={active}/>;
  const actions = (
    <div className="d-flex justify-content-end align-items-center">
      <Button className="mr-4">Reorganize</Button>
      <Button icon="get_app">Export to PDF</Button>
    </div>
  );

  return (
    <Row>
      <Column size={11}>
        <div className="bg-secondary-lightest">
          <PageHeader
            title="Dashboard"
            separator={false}
            navigation={navigation}
            actions={actions}
          />
        </div>
      </Column>
    </Row>
  );
}
```


#### Components PageHeader Level 0 With Stepper

```jsx
import { Stepper, Button, PageHeader } from '@innovaccer/design-system';

() => {
  const title = 'Annual Wellness Visit';

  const stepperData = [
    {
      value: 'step_1',
      label: 'Recipients',
    },
    {
      value: 'step_2',
      label: 'Message'
    },
    {
      value: 'step_3',
      label: 'Schedule',
    }
  ];

  const [active, setActive] = React.useState(2);

  const onChangeHandler = (activeStep) => {
    setActive(activeStep)
  };

  const options = {
    title,
    separator: false,
    stepper: <Stepper steps={stepperData} onChange={onChangeHandler} active={active} completed={1} />,
    actions: <Button>Finish later</Button>
  };

  return (
    <div className="w-100 bg-secondary-lightest">
      <PageHeader {...options} />
    </div>
  );
}
```


#### Components PageHeader Level 0 With Tabs

```jsx
import { Tabs, Button, Row, Column, PageHeader } from '@innovaccer/design-system';

() => {
  const tabs = [
    {
      count: 4,
      label: 'Current'
    },
    {
      count: 4,
      label: 'Invited'
    },
    {
      count: 4,
      label: 'Inactive'
    }
  ];

  const [activeIndex, setActiveIndex] = React.useState(0);

  const tab = (
    <Tabs
      tabs={tabs}
      activeIndex={activeIndex}
      onTabChange={setActiveIndex}
    />
  );

  const actions = (
    <div className="d-flex justify-content-end align-items-center">
      <Button icon="get_app" className="mr-4">Download Records</Button>
      <Button appearance="primary">Invite users</Button>
    </div>
  );

  return (
    <Row>
      <Column size={11}>
        <div className="bg-secondary-lightest">
          <PageHeader
            title="Users"
            separator={true}
            tabs={tab}
            actions={actions}
          />
        </div>
      </Column>
    </Row>
  );
}
```


#### Components PageHeader Level 1 With back button With Navigation

```jsx
import { HorizontalNav, Text, AvatarGroup, Menu, Button, Badge, StatusHint, PageHeader } from '@innovaccer/design-system';

/*
// style.css
.Pageheader-longWrapper {
    width: 1200px;
}

*/

() => {
  const options = [
    {
      label: 'Option 1',
      value: 'Option 1',
    },
    {
      label: 'Option 2',
      value: 'Option 2',
    },
    {
      label: 'Option 3',
      value: 'Option 3',
    },
  ];

  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
  ];

  const navigationData = [
    {
      name: 'menu_1',
      label: 'Virtual Visits',
    },
    {
      name: 'menu_2',
      label: 'Assesments',
    },
  ];

  const [active, setActive] = React.useState({
    name: 'menu_1',
  });

  const onClickHandler = (menu) => {
    setActive(menu);
  };

  const navigation = <HorizontalNav menus={navigationData} onClick={onClickHandler} active={active} />;

  const actions = (
    <div className="d-flex justify-content-end align-items-center">
      <Text appearance="subtle" className="mr-4">Few minutes ago</Text>
      <AvatarGroup borderColor="var(--secondary-lightest)" className="mr-4" list={list} popoverOptions={{ dark: true, on: 'hover', position: 'bottom' }} />
      <div className="mr-4">
        <Menu trigger={<Menu.Trigger />}>
          <Menu.List>
            {
              options.map((item, key) => {
                const { label } = item;
                return (
                  <Menu.Item key={key}>
                    {label}
                  </Menu.Item>
                );
              })
            }
          </Menu.List>
        </Menu>
      </div>
      <Button className="mr-4">Finish later</Button>
      <Button appearance="primary" onClick={onClickHandler}>
        Next
      </Button>
    </div>
  );

  const badge = <Badge appearance="success" subtle={true}>Sent</Badge>;
  const button = <Button icon="arrow_back" size="tiny" largeIcon={true} />;
  const status = <StatusHint appearance="info">Ongoing</StatusHint>;

  return (
    <div className="bg-secondary-lightest Pageheader-longWrapper">
      <PageHeader
        title="Annual Wellness"
        separator={false}
        navigationPosition="center"
        navigation={navigation}
        actions={actions}
        badge={badge}
        status={status}
        button={button}
      />
    </div>
  );
}
```


#### Components PageHeader Level 1 With back button With Stepper

```jsx
import { Stepper, Text, AvatarGroup, Menu, Button, Badge, MetaList, PageHeader } from '@innovaccer/design-system';

/*
// style.css
.Pageheader-longWrapper {
    width: 1200px;
}

*/

() => {
  const stepperData = [
    {
      value: 'step_1',
      label: 'Recipients',
    },
    {
      value: 'step_2',
      label: 'Message'
    },
    {
      value: 'step_3',
      label: 'Schedule',
    }
  ];

  const options = [
    {
      label: 'Option 1',
      value: 'Option 1',
    },
    {
      label: 'Option 2',
      value: 'Option 2',
    },
    {
      label: 'Option 3',
      value: 'Option 3',
    }
  ];

  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler',
    },
  ];

  const [active, setActive] = React.useState(2);

  const onChangeHandler = (activeStep) => {
    setActive(activeStep);
  };

  const stepper = <Stepper steps={stepperData} onChange={onChangeHandler} active={active} completed={1} />;
  const actions = (
    <div className="d-flex justify-content-end align-items-center">
      <Text appearance="subtle" className="mr-4">Few minutes ago</Text>
      <AvatarGroup className="mr-4" list={list} borderColor="var(--secondary-lightest)" popoverOptions={{ dark: true, on: 'hover', position: 'bottom' }} />
      <div className="mr-4">
        <Menu trigger={<Menu.Trigger />}>
          <Menu.List>
            {
              options.map((item, key) => {
                const { label } = item;
                return (
                  <Menu.Item key={key}>
                    {label}
                  </Menu.Item>
                );
              })
            }
          </Menu.List>
        </Menu>
      </div>
      <Button className="mr-4">Finish later</Button>
    </div>
  );

  const badge = (
    <Badge appearance="secondary">Message</Badge>
  );

  const meta = (
    <MetaList
      list={[{ label: 'Draft' }]}
      seperator={false}
    />
  );

  const button = <Button icon="arrow_back" size="tiny" largeIcon={true} />;

  return (
    <div className="bg-secondary-lightest Pageheader-longWrapper">
      <PageHeader
        title="Annual Wellness Visit"
        separator={false}
        navigationPosition="center"
        stepper={stepper}
        actions={actions}
        button={button}
        badge={badge}
        meta={meta}
      />
    </div>
  );
}
```


#### Components PageHeader Level 1 With back button With Tabs

```jsx
import { Tabs, Text, AvatarGroup, Menu, Button, PageHeader } from '@innovaccer/design-system';

/*
// style.css
.Pageheader-longWrapper {
    width: 1200px;
}

*/

() => {
  const options = [
    {
      label: 'Option 1',
      value: 'Option 1',
    },
    {
      label: 'Option 2',
      value: 'Option 2',
    },
    {
      label: 'Option 3',
      value: 'Option 3',
    },
  ];

  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
  ];

  const tabs = [
    {
      count: 32,
      label: 'New',
    },
    {
      count: 4,
      label: 'Invalid',
    },
    {
      count: 2,
      label: 'Duplicate',
    },
  ];

  const [activeIndex, setActiveIndex] = React.useState(0);

  const tab = <Tabs tabs={tabs} activeIndex={activeIndex} onTabChange={setActiveIndex} />;

  const actions = (
    <div className="d-flex justify-content-end align-items-center">
      <Text appearance="subtle" className="mr-4">Few minutes ago</Text>
      <AvatarGroup borderColor="var(--secondary-lightest)" className="mr-4" list={list} popoverOptions={{ dark: true, on: 'hover', position: 'bottom' }} />
      <div className="mr-4">
        <Menu trigger={<Menu.Trigger />}>
          <Menu.List>
            {
              options.map((item, key) => {
                const { label } = item;
                return (
                  <Menu.Item key={key}>
                    {label}
                  </Menu.Item>
                );
              })
            }
          </Menu.List>
        </Menu>
      </div>
      <Button className="mr-4">Finish later</Button>
      <Button appearance="primary">Next</Button>
    </div>
  );

  const button = <Button icon="arrow_back" size="tiny" largeIcon={true} />;

  return (
    <div className="bg-secondary-lightest Pageheader-longWrapper">
      <PageHeader
        title="Sender creation report"
        tabs={tab}
        actions={actions}
        button={button}
      />
    </div>
  );
}
```


#### Components PageHeader Level 1 With breadcrumb With Navigation

```jsx
import { HorizontalNav, Breadcrumbs, Badge, MetaList, StatusHint, Row, Column, PageHeader } from '@innovaccer/design-system';

() => {
  const navigationData = [
    {
      name: 'menu_1',
      label: 'Performance',
    },
    {
      name: 'menu_2',
      label: 'Recipients'
    }
  ];

  const [active, setActive] = React.useState({
    name: 'menu_1'
  });

  const onClickHandler = (menu) => {
    setActive(menu);
  };

  const navigation = (
    <HorizontalNav
      menus={navigationData}
      onClick={onClickHandler}
      active={active}
    />
  );
  const actions = (
    <div className="d-flex justify-content-end align-items-center"/>
  );
  const breadcrumbs = (
    <Breadcrumbs
      list={[{
        label: 'Outreach',
        link: '/Outreach'
      }]}
      onClick={link => console.log(`on-click: ${link}`)}
    />
  );
  const badge = (
    <Badge subtle={true} appearance="success">Sent</Badge>
  );
  const meta = (
    <MetaList
      list={[{ label: 'Text' }, { label: 'Email' }]}
    />
  );

  const status = <StatusHint appearance="info">Ongoing</StatusHint>;

  return (
    <Row>
      <Column size={11}>
        <div className="bg-secondary-lightest">
          <PageHeader
            title="Covid-19"
            separator={false}
            navigationPosition="center"
            navigation={navigation}
            actions={actions}
            breadcrumbs={breadcrumbs}
            badge={badge}
            status={status}
            meta={meta}
          />
        </div>
      </Column>
    </Row>
  );
}
```


#### Components PageHeader Level 1 With breadcrumb With Stepper

```jsx
import { Stepper, Text, AvatarGroup, Menu, Button, Breadcrumbs, Badge, MetaList, PageHeader } from '@innovaccer/design-system';

/*
// style.css
.Pageheader-longWrapper {
    width: 1200px;
}

*/

() => {
  const stepperData = [
    {
      value: 'step_1',
      label: 'Recipients',
    },
    {
      value: 'step_2',
      label: 'Message'
    },
    {
      value: 'step_3',
      label: 'Schedule',
    }
  ];

  const options = [
    {
      label: 'Option 1',
      value: 'Option 1',
    },
    {
      label: 'Option 2',
      value: 'Option 2',
    },
    {
      label: 'Option 3',
      value: 'Option 3',
    }
  ];

  const avatarList = [
    {
      firstName: 'John',
      lastName: 'Doe',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
    },
    {
      firstName: 'Nancy',
      lastName: 'Wheeler',
    },
    {
      firstName: 'Monica',
      lastName: 'Geller',
    },
    {
      firstName: 'Arya',
      lastName: 'Stark',
    },
    {
      firstName: 'Rachel',
      lastName: 'Green',
    },
    {
      firstName: 'Walter',
      lastName: 'Wheeler',
    },
  ];

  const [active, setActive] = React.useState(2);

  const onChangeHandler = (activeStep) => {
    setActive(activeStep);
  };

  const stepper = <Stepper steps={stepperData} onChange={onChangeHandler} active={active} completed={1} />;
  const actions = (
    <div className="d-flex justify-content-end align-items-center">
      <Text appearance="subtle" className="mr-4">Few minutes ago</Text>
      <AvatarGroup
        className="mr-4"
        list={avatarList}
        borderColor="var(--secondary-lightest)"
        popoverOptions={{ dark: true, on: 'hover', position: 'bottom' }}
      />
      <div className="mr-4">
       <Menu trigger={<Menu.Trigger />}>
        <Menu.List>
          {
            options.map((item, key) => {
              const { label } = item;
              return (
                <Menu.Item key={key}>
                  {label}
                </Menu.Item>
              );
            })
          }
        </Menu.List>
      </Menu>
      </div>
      <Button className="mr-4">Finish later</Button>
    </div>
  );
  const breadcrumbs = (
    <Breadcrumbs
      list={[{
        label: 'Campaigns',
        link: '/Campaigns'
      }]}
      onClick={link => console.log(`on-click: ${link}`)}
    />
  );
  const badge = (
    <Badge appearance="secondary">Message</Badge>
  );
  const meta = (
    <MetaList
      list={[{ label: 'Draft' }]}
      seperator={false}
    />
  );

  return (
    <div className="bg-secondary-lightest Pageheader-longWrapper">
      <PageHeader
        title="Annual Wellness Visit"
        separator={false}
        navigationPosition="center"
        stepper={stepper}
        actions={actions}
        breadcrumbs={breadcrumbs}
        badge={badge}
        meta={meta}
      />
    </div>
  );
}
```


#### Components PageHeader Level 1 With breadcrumb With Tabs

```jsx
import { Tabs, Breadcrumbs, Row, Column, PageHeader } from '@innovaccer/design-system';

() => {
  const tabs = [
    {
      count: 32,
      label: 'New'
    },
    {
      count: 4,
      label: 'Invalid'
    },
    {
      count: 2,
      label: 'Duplicate'
    }
  ];

  const [activeIndex, setActiveIndex] = React.useState(0);

  const tab = (
    <Tabs
      tabs={tabs}
      activeIndex={activeIndex}
      onTabChange={setActiveIndex}
    />
  );

  const breadcrumbs = (
    <Breadcrumbs
      list={[{
        label: 'Senders',
        link: '/Senders'
      }]}
      onClick={link => console.log(`on-click: ${link}`)}
    />
  );

  return (
    <Row>
      <Column size={11}>
        <div className="bg-secondary-lightest">
          <PageHeader
            title="Sender creation report"
            separator={true}
            tabs={tab}
            breadcrumbs={breadcrumbs}
          />
        </div>
      </Column>
    </Row>
  );
}
```


#### Components PageHeader Responsiveness

```jsx
import { Text, AvatarGroup, Menu, Icon, Breadcrumbs, StatusHint, HorizontalNav, PageHeader } from '@innovaccer/design-system';

() => {
  const navigationData = [
    {
      name: 'menu_1',
      label: 'Interventions',
    },
    {
      name: 'menu_2',
      label: 'No Linked Activites'
    }
  ];

  const list = [
    {
      firstName: 'John',
      lastName: 'Doe',
      appearance: 'accent2',
    },
    {
      firstName: 'Steven',
      lastName: 'Packton',
      appearance: 'accent3',
    }
  ];

  const options = [
    {
      icon: 'print',
      label: 'Edit',
      value: 'Edit',
    },
    {
      icon: 'assignment_turned_in',
      label: 'Complete',
      value: 'Complete',
    },
  ];

  const [active, setActive] = React.useState({
    name: 'menu_1'
  });

  const onClickHandler = (menu) => {
    setActive(menu);
  };

  const actions = (
    <div className="d-flex justify-content-end align-items-center">
    <Text appearance="subtle" className="mr-4">Updated 1 day ago</Text>
    <AvatarGroup borderColor="var(--secondary-lightest)" className="mr-5" list={list}/>
    <div>
        <Menu trigger={<Menu.Trigger />}>
          <Menu.List>
            <Menu.Item className="d-flex align-items-center">
              <Icon name="print" className="mr-4 my-2" />
              <Text>Edit</Text>
            </Menu.Item>
            <Menu.Item className="d-flex align-items-center">
              <Icon name="assignment_turned_in" className="mr-4 my-2" />
              <Text>Complete</Text>
            </Menu.Item>
          </Menu.List>
      </Menu>
    </div>
    </div>
  );

  const breadcrumbs = (
    <Breadcrumbs
      list={[{
        label: 'Care potential',
        link: '/Care potential'
      }]}
      onClick={link => console.log(`on-click: ${link}`)}
    />
  );

  const status = (
    <StatusHint appearance="info">Ongoing</StatusHint>
  );

  const navigation = (
    <HorizontalNav 
      menus={navigationData}
      onClick={onClickHandler}
      active={active}
    />
  );

  return (
    <div className="bg-secondary-lightest">
      <PageHeader
        navigationPosition="bottom"
        title="Pac Follow-Up Protocol"
        separator={false}
        navigation={navigation}
        actions={actions}
        breadcrumbs={breadcrumbs}
        status={status}
      />
    </div>
  );
}
```# Pagination

Pagination is used to split a list of items into pages and jump to the next/previous or a specific page for ease of navigation.

### Code Examples

#### Pagination

```jsx
import { Pagination } from '@innovaccer/design-system';

() => {
  return (
    <Pagination
      type= "basic"
      page= {1}
      totalPages={50}
      onPageChange={pageNo => console.log(pageNo)}
    />
  );
}
```


#### Pagination

```jsx
import { Pagination } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <div className="d-flex flex-column align-items-center">
        <Pagination
          type="jump"
          page={1}
          totalPages={50}
          onPageChange={(pageNo) => console.log(pageNo) }
        />
      </div>
     </div>
  );
}
```


#### Basic Pagination in Table

```jsx
import { Icon, GridCell, Card, Table } from '@innovaccer/design-system';


() => {
  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Carin",
        "lastName": "Robiou",
        "email": "crobioua@skype.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Anson",
        "lastName": "Gamon",
        "email": "agamonb@economist.com",
        "gender": "Male"
    },
    {
        "firstName": "Brina",
        "lastName": "Pirie",
        "email": "bpiriec@stumbleupon.com",
        "gender": "Female"
    },
    {
        "firstName": "Hermy",
        "lastName": "Dyett",
        "email": "hdyettd@boston.com",
        "gender": "Male"
    },
    {
        "firstName": "Aime",
        "lastName": "von Hagt",
        "email": "avonhagte@nyu.edu",
        "gender": "Female"
    },
    {
        "firstName": "Gusti",
        "lastName": "Haycock",
        "email": "ghaycockf@virginia.edu",
        "gender": "Female"
    },
    {
        "firstName": "Mortimer",
        "lastName": "Kunneke",
        "email": "mkunnekeg@weather.com",
        "gender": "Male"
    },
    {
        "firstName": "Barnie",
        "lastName": "Pohls",
        "email": "bpohlsh@columbia.edu",
        "gender": "Male"
    },
    {
        "firstName": "Elliot",
        "lastName": "Nealey",
        "email": "enealeyi@cocolog-nifty.com",
        "gender": "Male"
    },
    {
        "firstName": "Allsun",
        "lastName": "Gong",
        "email": "agongj@discuz.net",
        "gender": "Female"
    },
    {
        "firstName": "Harwell",
        "lastName": "Kegan",
        "email": "hkegank@domainmarket.com",
        "gender": "Male"
    },
    {
        "firstName": "Gilles",
        "lastName": "Sandell",
        "email": "gsandelll@apache.org",
        "gender": "Male"
    },
    {
        "firstName": "Hilliard",
        "lastName": "Beamish",
        "email": "hbeamishm@shop-pro.jp",
        "gender": "Male"
    },
    {
        "firstName": "Charley",
        "lastName": "Kuschek",
        "email": "ckuschekn@dropbox.com",
        "gender": "Male"
    },
    {
        "firstName": "Danny",
        "lastName": "Churchin",
        "email": "dchurchino@bbc.co.uk",
        "gender": "Female"
    },
    {
        "firstName": "Ervin",
        "lastName": "Chatelain",
        "email": "echatelainp@mac.com",
        "gender": "Male"
    },
    {
        "firstName": "Milli",
        "lastName": "Joseph",
        "email": "mjosephq@merriam-webster.com",
        "gender": "Female"
    },
    {
        "firstName": "Greer",
        "lastName": "O'Doherty",
        "email": "godohertyr@homestead.com",
        "gender": "Female"
    },
    {
        "firstName": "Haroun",
        "lastName": "Martensen",
        "email": "hmartensens@skype.com",
        "gender": "Male"
    },
    {
        "firstName": "Desiree",
        "lastName": "Colwell",
        "email": "dcolwellt@businessinsider.com",
        "gender": "Female"
    },
    {
        "firstName": "Almeda",
        "lastName": "Jowsey",
        "email": "ajowseyu@ask.com",
        "gender": "Female"
    },
    {
        "firstName": "Cinderella",
        "lastName": "Dunnet",
        "email": "cdunnetv@mac.com",
        "gender": "Female"
    },
    {
        "firstName": "Hubert",
        "lastName": "Legion",
        "email": "hlegionw@ameblo.jp",
        "gender": "Male"
    },
    {
        "firstName": "Costa",
        "lastName": "Adamovsky",
        "email": "cadamovskyx@joomla.org",
        "gender": "Male"
    },
    {
        "firstName": "Kristan",
        "lastName": "Bielfeld",
        "email": "kbielfeldy@live.com",
        "gender": "Female"
    },
    {
        "firstName": "Sammy",
        "lastName": "Shermore",
        "email": "sshermorez@washington.edu",
        "gender": "Female"
    },
    {
        "firstName": "Kathi",
        "lastName": "Dowyer",
        "email": "kdowyer10@bluehost.com",
        "gender": "Female"
    },
    {
        "firstName": "Kennith",
        "lastName": "Whitehouse",
        "email": "kwhitehouse11@cornell.edu",
        "gender": "Male"
    },
    {
        "firstName": "Brianna",
        "lastName": "Garland",
        "email": "bgarland12@wikipedia.org",
        "gender": "Female"
    },
    {
        "firstName": "Cristobal",
        "lastName": "Mapholm",
        "email": "cmapholm13@constantcontact.com",
        "gender": "Male"
    },
    {
        "firstName": "Zia",
        "lastName": "Harrowing",
        "email": "zharrowing14@huffingtonpost.com",
        "gender": "Female"
    },
    {
        "firstName": "Zabrina",
        "lastName": "Gravener",
        "email": "zgravener15@ameblo.jp",
        "gender": "Female"
    },
    {
        "firstName": "Gregoor",
        "lastName": "Cruz",
        "email": "gcruz16@uol.com.br",
        "gender": "Male"
    },
    {
        "firstName": "Julita",
        "lastName": "Gemeau",
        "email": "jgemeau17@bandcamp.com",
        "gender": "Female"
    },
    {
        "firstName": "Gilbert",
        "lastName": "Sallier",
        "email": "gsallier18@dailymail.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Bride",
        "lastName": "Boniface",
        "email": "bboniface19@howstuffworks.com",
        "gender": "Female"
    },
    {
        "firstName": "Rodolph",
        "lastName": "Mattussevich",
        "email": "rmattussevich1a@nymag.com",
        "gender": "Male"
    },
    {
        "firstName": "Rowan",
        "lastName": "Rizon",
        "email": "rrizon1b@thetimes.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Avie",
        "lastName": "Nicolls",
        "email": "anicolls1c@nbcnews.com",
        "gender": "Female"
    },
    {
        "firstName": "Bram",
        "lastName": "Kleinhaut",
        "email": "bkleinhaut1d@imdb.com",
        "gender": "Male"
    },
    {
        "firstName": "Carmita",
        "lastName": "Costin",
        "email": "ccostin1e@hibu.com",
        "gender": "Female"
    },
    {
        "firstName": "Wash",
        "lastName": "Vannuchi",
        "email": "wvannuchi1f@japanpost.jp",
        "gender": "Male"
    },
    {
        "firstName": "Nikki",
        "lastName": "Faye",
        "email": "nfaye1g@feedburner.com",
        "gender": "Female"
    },
    {
        "firstName": "Aron",
        "lastName": "Scimonelli",
        "email": "ascimonelli1h@nationalgeographic.com",
        "gender": "Male"
    },
    {
        "firstName": "Smitty",
        "lastName": "Giacomello",
        "email": "sgiacomello1i@google.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Staci",
        "lastName": "D'Elias",
        "email": "sdelias1j@paginegialle.it",
        "gender": "Female"
    },
    {
        "firstName": "Radcliffe",
        "lastName": "Garbutt",
        "email": "rgarbutt1k@thetimes.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Maxwell",
        "lastName": "Krikorian",
        "email": "mkrikorian1l@ask.com",
        "gender": "Male"
    },
    {
        "firstName": "Dunstan",
        "lastName": "Chansonne",
        "email": "dchansonne1m@posterous.com",
        "gender": "Male"
    },
    {
        "firstName": "Isaak",
        "lastName": "Faherty",
        "email": "ifaherty1n@who.int",
        "gender": "Male"
    },
    {
        "firstName": "Sawyere",
        "lastName": "Ede",
        "email": "sede1o@drupal.org",
        "gender": "Male"
    },
    {
        "firstName": "Perren",
        "lastName": "Daddow",
        "email": "pdaddow1p@indiegogo.com",
        "gender": "Male"
    },
    {
        "firstName": "Brendis",
        "lastName": "Napier",
        "email": "bnapier1q@multiply.com",
        "gender": "Male"
    },
    {
        "firstName": "Francene",
        "lastName": "Godbold",
        "email": "fgodbold1r@joomla.org",
        "gender": "Female"
    },
    {
        "firstName": "Moll",
        "lastName": "Fludgate",
        "email": "mfludgate1s@who.int",
        "gender": "Female"
    },
    {
        "firstName": "Allayne",
        "lastName": "Medhurst",
        "email": "amedhurst1t@is.gd",
        "gender": "Male"
    },
    {
        "firstName": "Genvieve",
        "lastName": "Mellows",
        "email": "gmellows1u@stumbleupon.com",
        "gender": "Female"
    },
    {
        "firstName": "Rebe",
        "lastName": "Durnford",
        "email": "rdurnford1v@biglobe.ne.jp",
        "gender": "Female"
    },
    {
        "firstName": "Thalia",
        "lastName": "Joerning",
        "email": "tjoerning1w@netscape.com",
        "gender": "Female"
    },
    {
        "firstName": "Beckie",
        "lastName": "Lammin",
        "email": "blammin1x@gnu.org",
        "gender": "Female"
    },
    {
        "firstName": "Kassandra",
        "lastName": "Furney",
        "email": "kfurney1y@surveymonkey.com",
        "gender": "Female"
    },
    {
        "firstName": "Libbie",
        "lastName": "Gladyer",
        "email": "lgladyer1z@dropbox.com",
        "gender": "Female"
    },
    {
        "firstName": "Kai",
        "lastName": "Goldsbury",
        "email": "kgoldsbury20@census.gov",
        "gender": "Female"
    },
    {
        "firstName": "Arielle",
        "lastName": "De Bell",
        "email": "adebell21@addthis.com",
        "gender": "Female"
    },
    {
        "firstName": "Ellary",
        "lastName": "Warnock",
        "email": "ewarnock22@ted.com",
        "gender": "Male"
    },
    {
        "firstName": "Skelly",
        "lastName": "Blakes",
        "email": "sblakes23@reddit.com",
        "gender": "Male"
    },
    {
        "firstName": "Roanne",
        "lastName": "Stanyforth",
        "email": "rstanyforth24@com.com",
        "gender": "Female"
    },
    {
        "firstName": "Cash",
        "lastName": "Fettis",
        "email": "cfettis25@go.com",
        "gender": "Male"
    },
    {
        "firstName": "Farleigh",
        "lastName": "McDavid",
        "email": "fmcdavid26@sbwire.com",
        "gender": "Male"
    },
    {
        "firstName": "Holly",
        "lastName": "Barfford",
        "email": "hbarfford27@wsj.com",
        "gender": "Female"
    },
    {
        "firstName": "Hurley",
        "lastName": "Benaine",
        "email": "hbenaine28@sun.com",
        "gender": "Male"
    },
    {
        "firstName": "Maryjo",
        "lastName": "Gilhooly",
        "email": "mgilhooly29@tripod.com",
        "gender": "Female"
    },
    {
        "firstName": "Annis",
        "lastName": "Linkie",
        "email": "alinkie2a@wp.com",
        "gender": "Female"
    },
    {
        "firstName": "Mariel",
        "lastName": "Husher",
        "email": "mhusher2b@etsy.com",
        "gender": "Female"
    },
    {
        "firstName": "Niels",
        "lastName": "Klimontovich",
        "email": "nklimontovich2c@surveymonkey.com",
        "gender": "Male"
    },
    {
        "firstName": "Udall",
        "lastName": "Linfitt",
        "email": "ulinfitt2d@toplist.cz",
        "gender": "Male"
    },
    {
        "firstName": "Isidore",
        "lastName": "Kuhn",
        "email": "ikuhn2e@cdc.gov",
        "gender": "Male"
    },
    {
        "firstName": "Rosemonde",
        "lastName": "Kettle",
        "email": "rkettle2f@techcrunch.com",
        "gender": "Female"
    },
    {
        "firstName": "Cass",
        "lastName": "Boot",
        "email": "cboot2g@furl.net",
        "gender": "Male"
    },
    {
        "firstName": "Montague",
        "lastName": "Rossey",
        "email": "mrossey2h@goo.gl",
        "gender": "Male"
    },
    {
        "firstName": "Geno",
        "lastName": "Jenkyn",
        "email": "gjenkyn2i@opensource.org",
        "gender": "Male"
    },
    {
        "firstName": "Esdras",
        "lastName": "Skivington",
        "email": "eskivington2j@answers.com",
        "gender": "Male"
    },
    {
        "firstName": "Gabriello",
        "lastName": "Luce",
        "email": "gluce2k@nydailynews.com",
        "gender": "Male"
    },
    {
        "firstName": "Magdalene",
        "lastName": "Ilyunin",
        "email": "milyunin2l@prweb.com",
        "gender": "Female"
    },
    {
        "firstName": "Isidro",
        "lastName": "Fawson",
        "email": "ifawson2m@squidoo.com",
        "gender": "Male"
    },
    {
        "firstName": "Blinny",
        "lastName": "Palfrey",
        "email": "bpalfrey2n@networksolutions.com",
        "gender": "Female"
    },
    {
        "firstName": "Justen",
        "lastName": "Kordas",
        "email": "jkordas2o@symantec.com",
        "gender": "Male"
    },
    {
        "firstName": "Damien",
        "lastName": "Hallede",
        "email": "dhallede2p@unicef.org",
        "gender": "Male"
    },
    {
        "firstName": "Jaquelyn",
        "lastName": "Rockhall",
        "email": "jrockhall2q@vkontakte.ru",
        "gender": "Female"
    },
    {
        "firstName": "Garrek",
        "lastName": "Matignon",
        "email": "gmatignon2r@noaa.gov",
        "gender": "Male"
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      cellType: 'WITH_META_LIST',
      sorting: false,
      cellRenderer: props => {
        return (
          <>
            <Icon className="mr-5" name="events" />
            <GridCell
              {...props}
              schema={{
                ...props.schema,
                name: 'email'
              }}
            />
          </>
        );
      }
    },
  ];

  return (
    <div className="vh-50">
      <Card className="h-100 overflow-hidden">
        <Table
          data={data}
          pageSize={6}
          schema={schema}
          withPagination={true}
          paginationType={'basic'}
        />
      </Card>
    </div>
  );
};

```


#### Jump Pagination in Table

```jsx
import { Icon, GridCell, Card, Table } from '@innovaccer/design-system';


() => {
  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Carin",
        "lastName": "Robiou",
        "email": "crobioua@skype.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Anson",
        "lastName": "Gamon",
        "email": "agamonb@economist.com",
        "gender": "Male"
    },
    {
        "firstName": "Brina",
        "lastName": "Pirie",
        "email": "bpiriec@stumbleupon.com",
        "gender": "Female"
    },
    {
        "firstName": "Hermy",
        "lastName": "Dyett",
        "email": "hdyettd@boston.com",
        "gender": "Male"
    },
    {
        "firstName": "Aime",
        "lastName": "von Hagt",
        "email": "avonhagte@nyu.edu",
        "gender": "Female"
    },
    {
        "firstName": "Gusti",
        "lastName": "Haycock",
        "email": "ghaycockf@virginia.edu",
        "gender": "Female"
    },
    {
        "firstName": "Mortimer",
        "lastName": "Kunneke",
        "email": "mkunnekeg@weather.com",
        "gender": "Male"
    },
    {
        "firstName": "Barnie",
        "lastName": "Pohls",
        "email": "bpohlsh@columbia.edu",
        "gender": "Male"
    },
    {
        "firstName": "Elliot",
        "lastName": "Nealey",
        "email": "enealeyi@cocolog-nifty.com",
        "gender": "Male"
    },
    {
        "firstName": "Allsun",
        "lastName": "Gong",
        "email": "agongj@discuz.net",
        "gender": "Female"
    },
    {
        "firstName": "Harwell",
        "lastName": "Kegan",
        "email": "hkegank@domainmarket.com",
        "gender": "Male"
    },
    {
        "firstName": "Gilles",
        "lastName": "Sandell",
        "email": "gsandelll@apache.org",
        "gender": "Male"
    },
    {
        "firstName": "Hilliard",
        "lastName": "Beamish",
        "email": "hbeamishm@shop-pro.jp",
        "gender": "Male"
    },
    {
        "firstName": "Charley",
        "lastName": "Kuschek",
        "email": "ckuschekn@dropbox.com",
        "gender": "Male"
    },
    {
        "firstName": "Danny",
        "lastName": "Churchin",
        "email": "dchurchino@bbc.co.uk",
        "gender": "Female"
    },
    {
        "firstName": "Ervin",
        "lastName": "Chatelain",
        "email": "echatelainp@mac.com",
        "gender": "Male"
    },
    {
        "firstName": "Milli",
        "lastName": "Joseph",
        "email": "mjosephq@merriam-webster.com",
        "gender": "Female"
    },
    {
        "firstName": "Greer",
        "lastName": "O'Doherty",
        "email": "godohertyr@homestead.com",
        "gender": "Female"
    },
    {
        "firstName": "Haroun",
        "lastName": "Martensen",
        "email": "hmartensens@skype.com",
        "gender": "Male"
    },
    {
        "firstName": "Desiree",
        "lastName": "Colwell",
        "email": "dcolwellt@businessinsider.com",
        "gender": "Female"
    },
    {
        "firstName": "Almeda",
        "lastName": "Jowsey",
        "email": "ajowseyu@ask.com",
        "gender": "Female"
    },
    {
        "firstName": "Cinderella",
        "lastName": "Dunnet",
        "email": "cdunnetv@mac.com",
        "gender": "Female"
    },
    {
        "firstName": "Hubert",
        "lastName": "Legion",
        "email": "hlegionw@ameblo.jp",
        "gender": "Male"
    },
    {
        "firstName": "Costa",
        "lastName": "Adamovsky",
        "email": "cadamovskyx@joomla.org",
        "gender": "Male"
    },
    {
        "firstName": "Kristan",
        "lastName": "Bielfeld",
        "email": "kbielfeldy@live.com",
        "gender": "Female"
    },
    {
        "firstName": "Sammy",
        "lastName": "Shermore",
        "email": "sshermorez@washington.edu",
        "gender": "Female"
    },
    {
        "firstName": "Kathi",
        "lastName": "Dowyer",
        "email": "kdowyer10@bluehost.com",
        "gender": "Female"
    },
    {
        "firstName": "Kennith",
        "lastName": "Whitehouse",
        "email": "kwhitehouse11@cornell.edu",
        "gender": "Male"
    },
    {
        "firstName": "Brianna",
        "lastName": "Garland",
        "email": "bgarland12@wikipedia.org",
        "gender": "Female"
    },
    {
        "firstName": "Cristobal",
        "lastName": "Mapholm",
        "email": "cmapholm13@constantcontact.com",
        "gender": "Male"
    },
    {
        "firstName": "Zia",
        "lastName": "Harrowing",
        "email": "zharrowing14@huffingtonpost.com",
        "gender": "Female"
    },
    {
        "firstName": "Zabrina",
        "lastName": "Gravener",
        "email": "zgravener15@ameblo.jp",
        "gender": "Female"
    },
    {
        "firstName": "Gregoor",
        "lastName": "Cruz",
        "email": "gcruz16@uol.com.br",
        "gender": "Male"
    },
    {
        "firstName": "Julita",
        "lastName": "Gemeau",
        "email": "jgemeau17@bandcamp.com",
        "gender": "Female"
    },
    {
        "firstName": "Gilbert",
        "lastName": "Sallier",
        "email": "gsallier18@dailymail.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Bride",
        "lastName": "Boniface",
        "email": "bboniface19@howstuffworks.com",
        "gender": "Female"
    },
    {
        "firstName": "Rodolph",
        "lastName": "Mattussevich",
        "email": "rmattussevich1a@nymag.com",
        "gender": "Male"
    },
    {
        "firstName": "Rowan",
        "lastName": "Rizon",
        "email": "rrizon1b@thetimes.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Avie",
        "lastName": "Nicolls",
        "email": "anicolls1c@nbcnews.com",
        "gender": "Female"
    },
    {
        "firstName": "Bram",
        "lastName": "Kleinhaut",
        "email": "bkleinhaut1d@imdb.com",
        "gender": "Male"
    },
    {
        "firstName": "Carmita",
        "lastName": "Costin",
        "email": "ccostin1e@hibu.com",
        "gender": "Female"
    },
    {
        "firstName": "Wash",
        "lastName": "Vannuchi",
        "email": "wvannuchi1f@japanpost.jp",
        "gender": "Male"
    },
    {
        "firstName": "Nikki",
        "lastName": "Faye",
        "email": "nfaye1g@feedburner.com",
        "gender": "Female"
    },
    {
        "firstName": "Aron",
        "lastName": "Scimonelli",
        "email": "ascimonelli1h@nationalgeographic.com",
        "gender": "Male"
    },
    {
        "firstName": "Smitty",
        "lastName": "Giacomello",
        "email": "sgiacomello1i@google.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Staci",
        "lastName": "D'Elias",
        "email": "sdelias1j@paginegialle.it",
        "gender": "Female"
    },
    {
        "firstName": "Radcliffe",
        "lastName": "Garbutt",
        "email": "rgarbutt1k@thetimes.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Maxwell",
        "lastName": "Krikorian",
        "email": "mkrikorian1l@ask.com",
        "gender": "Male"
    },
    {
        "firstName": "Dunstan",
        "lastName": "Chansonne",
        "email": "dchansonne1m@posterous.com",
        "gender": "Male"
    },
    {
        "firstName": "Isaak",
        "lastName": "Faherty",
        "email": "ifaherty1n@who.int",
        "gender": "Male"
    },
    {
        "firstName": "Sawyere",
        "lastName": "Ede",
        "email": "sede1o@drupal.org",
        "gender": "Male"
    },
    {
        "firstName": "Perren",
        "lastName": "Daddow",
        "email": "pdaddow1p@indiegogo.com",
        "gender": "Male"
    },
    {
        "firstName": "Brendis",
        "lastName": "Napier",
        "email": "bnapier1q@multiply.com",
        "gender": "Male"
    },
    {
        "firstName": "Francene",
        "lastName": "Godbold",
        "email": "fgodbold1r@joomla.org",
        "gender": "Female"
    },
    {
        "firstName": "Moll",
        "lastName": "Fludgate",
        "email": "mfludgate1s@who.int",
        "gender": "Female"
    },
    {
        "firstName": "Allayne",
        "lastName": "Medhurst",
        "email": "amedhurst1t@is.gd",
        "gender": "Male"
    },
    {
        "firstName": "Genvieve",
        "lastName": "Mellows",
        "email": "gmellows1u@stumbleupon.com",
        "gender": "Female"
    },
    {
        "firstName": "Rebe",
        "lastName": "Durnford",
        "email": "rdurnford1v@biglobe.ne.jp",
        "gender": "Female"
    },
    {
        "firstName": "Thalia",
        "lastName": "Joerning",
        "email": "tjoerning1w@netscape.com",
        "gender": "Female"
    },
    {
        "firstName": "Beckie",
        "lastName": "Lammin",
        "email": "blammin1x@gnu.org",
        "gender": "Female"
    },
    {
        "firstName": "Kassandra",
        "lastName": "Furney",
        "email": "kfurney1y@surveymonkey.com",
        "gender": "Female"
    },
    {
        "firstName": "Libbie",
        "lastName": "Gladyer",
        "email": "lgladyer1z@dropbox.com",
        "gender": "Female"
    },
    {
        "firstName": "Kai",
        "lastName": "Goldsbury",
        "email": "kgoldsbury20@census.gov",
        "gender": "Female"
    },
    {
        "firstName": "Arielle",
        "lastName": "De Bell",
        "email": "adebell21@addthis.com",
        "gender": "Female"
    },
    {
        "firstName": "Ellary",
        "lastName": "Warnock",
        "email": "ewarnock22@ted.com",
        "gender": "Male"
    },
    {
        "firstName": "Skelly",
        "lastName": "Blakes",
        "email": "sblakes23@reddit.com",
        "gender": "Male"
    },
    {
        "firstName": "Roanne",
        "lastName": "Stanyforth",
        "email": "rstanyforth24@com.com",
        "gender": "Female"
    },
    {
        "firstName": "Cash",
        "lastName": "Fettis",
        "email": "cfettis25@go.com",
        "gender": "Male"
    },
    {
        "firstName": "Farleigh",
        "lastName": "McDavid",
        "email": "fmcdavid26@sbwire.com",
        "gender": "Male"
    },
    {
        "firstName": "Holly",
        "lastName": "Barfford",
        "email": "hbarfford27@wsj.com",
        "gender": "Female"
    },
    {
        "firstName": "Hurley",
        "lastName": "Benaine",
        "email": "hbenaine28@sun.com",
        "gender": "Male"
    },
    {
        "firstName": "Maryjo",
        "lastName": "Gilhooly",
        "email": "mgilhooly29@tripod.com",
        "gender": "Female"
    },
    {
        "firstName": "Annis",
        "lastName": "Linkie",
        "email": "alinkie2a@wp.com",
        "gender": "Female"
    },
    {
        "firstName": "Mariel",
        "lastName": "Husher",
        "email": "mhusher2b@etsy.com",
        "gender": "Female"
    },
    {
        "firstName": "Niels",
        "lastName": "Klimontovich",
        "email": "nklimontovich2c@surveymonkey.com",
        "gender": "Male"
    },
    {
        "firstName": "Udall",
        "lastName": "Linfitt",
        "email": "ulinfitt2d@toplist.cz",
        "gender": "Male"
    },
    {
        "firstName": "Isidore",
        "lastName": "Kuhn",
        "email": "ikuhn2e@cdc.gov",
        "gender": "Male"
    },
    {
        "firstName": "Rosemonde",
        "lastName": "Kettle",
        "email": "rkettle2f@techcrunch.com",
        "gender": "Female"
    },
    {
        "firstName": "Cass",
        "lastName": "Boot",
        "email": "cboot2g@furl.net",
        "gender": "Male"
    },
    {
        "firstName": "Montague",
        "lastName": "Rossey",
        "email": "mrossey2h@goo.gl",
        "gender": "Male"
    },
    {
        "firstName": "Geno",
        "lastName": "Jenkyn",
        "email": "gjenkyn2i@opensource.org",
        "gender": "Male"
    },
    {
        "firstName": "Esdras",
        "lastName": "Skivington",
        "email": "eskivington2j@answers.com",
        "gender": "Male"
    },
    {
        "firstName": "Gabriello",
        "lastName": "Luce",
        "email": "gluce2k@nydailynews.com",
        "gender": "Male"
    },
    {
        "firstName": "Magdalene",
        "lastName": "Ilyunin",
        "email": "milyunin2l@prweb.com",
        "gender": "Female"
    },
    {
        "firstName": "Isidro",
        "lastName": "Fawson",
        "email": "ifawson2m@squidoo.com",
        "gender": "Male"
    },
    {
        "firstName": "Blinny",
        "lastName": "Palfrey",
        "email": "bpalfrey2n@networksolutions.com",
        "gender": "Female"
    },
    {
        "firstName": "Justen",
        "lastName": "Kordas",
        "email": "jkordas2o@symantec.com",
        "gender": "Male"
    },
    {
        "firstName": "Damien",
        "lastName": "Hallede",
        "email": "dhallede2p@unicef.org",
        "gender": "Male"
    },
    {
        "firstName": "Jaquelyn",
        "lastName": "Rockhall",
        "email": "jrockhall2q@vkontakte.ru",
        "gender": "Female"
    },
    {
        "firstName": "Garrek",
        "lastName": "Matignon",
        "email": "gmatignon2r@noaa.gov",
        "gender": "Male"
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      cellType: 'WITH_META_LIST',
      sorting: false,
      cellRenderer: props => {
        return (
          <>
            <Icon className="mr-5" name="events" />
            <GridCell
              {...props}
              schema={{
                ...props.schema,
                name: 'email'
              }}
            />
          </>
        );
      }
    },
  ];

  return (
    <div className="vh-50">
      <Card className="h-100 overflow-hidden">
        <Table
          data={data}
          pageSize={6}
          schema={schema}
          withPagination={true}
          paginationType={'jump'}
        />
      </Card>
    </div>
  );
};

```


#### Table without Pagination

```jsx
import { Icon, GridCell, Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '40%',
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
      cellType: 'WITH_META_LIST'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      cellType: 'WITH_META_LIST',
      sorting: false,
      cellRenderer: props => {
        return (
          <>
            <Icon className="mr-5" name="events" />
            <GridCell
              {...props}
              schema={{
                ...props.schema,
                name: 'email'
              }}
            />
          </>
        );
      }
    },
  ];

  const [error, setError] = React.useState(false);

  return (
    <div className="vh-75">
      <Card className="h-100 overflow-hidden">
        <Table
          error={error}
          data={data}
          schema={schema}
          withHeader={true}
          uniqueColumnName="email"
          withPagination={false}
          headerOptions={{
            withSearch: true,
            allowSelectAll: true,
          }}
          onSearch={(currData, searchTerm) => {
            console.log('onsearch called', searchTerm);
            setError(!error);
            return currData.filter(d =>
              d.firstName.toLowerCase().match(searchTerm.toLowerCase())
              || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
            );
          }}
          withCheckbox={true}
          onSelect={(rowIndex, selected, selectedList, selectAll) => console.log(`on-select:- rowIndex: ${rowIndex} selected: ${selected} selectedList: ${JSON.stringify(selectedList)} selectAll: ${selectAll}`)}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
    </div>
  );
};

```# Paragraph



### Code Examples

#### Paragraph

```jsx
import { Paragraph } from '@innovaccer/design-system';

() => {
  return <Paragraph>Paragraph component have different variants, look for options in knobs tab.</Paragraph>;
}
```


#### Paragraph

```jsx
import { Paragraph, Text } from '@innovaccer/design-system';

() => {
  const appearances = ['default', 'white', 'destructive', 'subtle', 'disabled'];
  return (
    <div className="d-flex">
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="mr-6">
            <div className={appear === 'white' ? 'bg-dark' : 'bg-transparent'}>
              <Paragraph appearance={appear}>Paragraph</Paragraph>
            </div>
            <br />
            <Text weight="strong">{appear.charAt(0).toUpperCase() + appear.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### Paragraph

```jsx
import { Paragraph } from '@innovaccer/design-system';

() => {
  const colorList = [
    [
      'primary',
      'primary-dark',
      'primary-darker',
      'primary-light',
      'primary-lighter',
      'primary-lightest',
      'primary-shadow',
    ],
    [
      'success',
      'success-dark',
      'success-darker',
      'success-light',
      'success-lighter',
      'success-lightest',
      'success-shadow',
    ],
    ['alert', 'alert-dark', 'alert-darker', 'alert-light', 'alert-lighter', 'alert-lightest', 'alert-shadow'],
    [
      'warning',
      'warning-dark',
      'warning-darker',
      'warning-light',
      'warning-lighter',
      'warning-lightest',
      'warning-shadow',
    ],
    [
      'accent1',
      'accent1-dark',
      'accent1-darker',
      'accent1-light',
      'accent1-lighter',
      'accent1-lightest',
      'accent1-shadow',
    ],
    [
      'accent2',
      'accent2-dark',
      'accent2-darker',
      'accent2-light',
      'accent2-lighter',
      'accent2-lightest',
      'accent2-shadow',
    ],
    [
      'accent3',
      'accent3-dark',
      'accent3-darker',
      'accent3-light',
      'accent3-lighter',
      'accent3-lightest',
      'accent3-shadow',
    ],
    [
      'accent4',
      'accent4-dark',
      'accent4-darker',
      'accent4-light',
      'accent4-lighter',
      'accent4-lightest',
      'accent4-shadow',
    ],
    ['white', 'inverse', 'inverse-light', 'inverse-lighter', 'inverse-lightest', 'inverse-shadow'],

    ['secondary', 'secondary-dark', 'secondary-light', 'secondary-lighter', 'secondary-lightest', 'secondary-shadow'],
  ];

  return (
    <div>
      {colorList.map((colors, key) => {
        return (
          <div key={key} className="d-flex justify-content-between w-100 py-4">
            {colors.map((color, ind) => {
              return (
                <Paragraph key={ind} color={color} className={color === 'white' ? 'bg-dark' : ''}>
                  {color}
                </Paragraph>
              );
            })}
          </div>
        );
      })}
    </div>
  );
}
```# Pills

Pill is used to highlight the count of an item.

### Code Examples

#### Components Pills All

```jsx
import { Pills } from '@innovaccer/design-system';

() => {
  return <Pills>10</Pills>;
}
```


#### Pills

```jsx
import { Pills } from '@innovaccer/design-system';

() => <Pills appearance="alert">10</Pills>
```


#### Pills

```jsx
import { Pills, Text } from '@innovaccer/design-system';

() => {
  const subtle = false;
  const weight = 'strong';
  const children = 10;
  const appearances = [
    'primary',
    'secondary',
    'alert',
    'warning',
    'success',
    'accent1',
    'accent2',
    'accent3',
    'accent4',
  ];

  return (
    <div className="d-flex">
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="mr-9">
            <Pills appearance={appear} subtle={subtle}>
              {children}
            </Pills>
            <br />
            <Text weight={weight}>{appear.charAt(0).toUpperCase() + appear.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### Pills

```jsx
import { Pills, Text } from '@innovaccer/design-system';

() => {
  const ButtonSubtle = true;
  const weight = 'strong';
  const children = 10;
  const appearances = [
    'primary',
    'secondary',
    'alert',
    'warning',
    'success',
    'accent1',
    'accent2',
    'accent3',
    'accent4',
  ];
  return (
    <div className="d-flex">
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="mr-9">
            <Pills appearance={appear} subtle={ButtonSubtle}>
              {children}
            </Pills>
            <br />
            <Text weight={weight}>{appear.charAt(0).toUpperCase() + appear.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### Pills

```jsx
import { Pills } from '@innovaccer/design-system';

() => {
  return (
    <Pills appearance="alert" subtle={true}>
      10
    </Pills>
  );
}
```# Placeholder



### Code Examples

#### Components Progress Indicators Placeholder All

```jsx
import { Placeholder, PlaceholderParagraph } from '@innovaccer/design-system';

() => {
  const withImage = false;
  const round = false;
  const imageSize = 'large';

  const options = {
    withImage,
    round,
    imageSize,
  };

  return (
    <Placeholder {...options}>
      <PlaceholderParagraph length="small" />
      <PlaceholderParagraph length="medium" />
    </Placeholder>
  );
}
```


#### PlaceholderImage

```jsx
import { PlaceholderImage, Text } from '@innovaccer/design-system';

() => {
  const size = 'medium';

  return (
    <div className="d-flex">
      <div className="mr-6">
        <PlaceholderImage size={size} round={false} />
        <br />
        <Text weight="strong">Square</Text>
      </div>
      <div>
        <PlaceholderImage size={size} round={true} />
        <br />
        <Text weight="strong">Round</Text>
      </div>
    </div>
  );
}
```


#### PlaceholderImage

```jsx
import { Text, PlaceholderImage } from '@innovaccer/design-system';

() => {
  const round = false;
  const sizes = ['small', 'medium', 'large'];
  const options = {
    round,
  };

  return (
    <div className="d-flex">
      {sizes.map((PlaceholderSize, ind) => {
        return (
          <div key={ind} className="mr-7">
            <Text weight="strong">{PlaceholderSize.charAt(0).toUpperCase() + PlaceholderSize.slice(1)}</Text>
            <PlaceholderImage size={PlaceholderSize} {...options} className="mt-5" />
          </div>
        );
      })}
    </div>
  );
}
```


#### Components Progress Indicators Placeholder Skeleton Loaders

```jsx
import { Card, Placeholder, PlaceholderParagraph } from '@innovaccer/design-system';

() => {
  return (
    <Card>
      <div className="px-6 py-5">
        <Placeholder round={true} imageSize="large">
          <PlaceholderParagraph length="large" size="m" />
          <PlaceholderParagraph size="m" />
        </Placeholder>
      </div>
      <div className="px-6 py-5 border-top">
        <Placeholder round={true} imageSize="large">
          <PlaceholderParagraph length="large" size="m" />
          <PlaceholderParagraph size="m" />
        </Placeholder>
      </div>
      <div className="px-6 py-5 border-top">
        <Placeholder round={true} imageSize="large">
          <PlaceholderParagraph length="large" size="m" />
          <PlaceholderParagraph size="m" />
        </Placeholder>
      </div>
      <div className="px-6 py-5 border-top">
        <Placeholder round={true} imageSize="large">
          <PlaceholderParagraph length="large" size="m" />
          <PlaceholderParagraph size="m" />
        </Placeholder>
      </div>
    </Card>
  );
}
```


#### PlaceholderParagraph

```jsx
import { PlaceholderParagraph } from '@innovaccer/design-system';

() => {
  const length = 'medium';
  const size = 'l';

  return <PlaceholderParagraph size={size} length={length} />;
}
```


#### PlaceholderParagraph

```jsx
import { PlaceholderParagraph, Text } from '@innovaccer/design-system';

() => {
  const lengths = ['small', 'medium', 'large'];

  return (
    <div>
      {lengths.map((len, ind) => {
        return (
          <div key={ind} className="mb-7">
            <PlaceholderParagraph length={len} />
            <Text weight="strong">{len.charAt(0).toUpperCase() + len.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### PlaceholderParagraph

```jsx
import { PlaceholderParagraph, Text } from '@innovaccer/design-system';

() => {
  const sizes = ['xxs', 'xs', 's', 'm', 'l', 'xl', 'xxl', 'xxxl'];

  return (
    <div>
      {sizes.map((s, ind) => {
        return (
          <div key={ind} className="mb-7">
            <PlaceholderParagraph size={s} />
            <Text weight="strong">{s}</Text>
          </div>
        );
      })}
    </div>
  );
}
```# Popover

Popover is used to display floating content in relation to a trigger, usually a button or link.

### Code Examples

#### Components Popover All

```jsx
import { Popover, Button, Text } from '@innovaccer/design-system';

() => {
  return(
    <div className='mb-11'>
      <Popover
        position="bottom-start"
        on="click"
        trigger={<Button appearance="basic">Open Popover</Button>}
      >
        <div className='p-5'>
        <Text>
          I am a popover, you can use me to display links,<br/> 
          interactive elements, avatars, text formatting, meta data
          etc.
        </Text>
        </div>
      </Popover>
    </div>
  );
}
```


#### Components Popover Dark Popover

```jsx
import { Popover, Button } from '@innovaccer/design-system';

() => (
  <div className="mb-9">
    <Popover
      position="bottom"
      on="click"
      trigger={<Button appearance="basic">Open Popover</Button>}
      dark={true}
      open={false}
    >
      <div className="p-10" />
    </Popover>
  </div>
)
```


#### Components Popover Disabled Trigger

```jsx
import { Popover, Button, Text } from '@innovaccer/design-system';

() => {
  const booleanValues = [false, true];

  return (
    <div className="mb-10 d-flex align-items-center w-100">
      {booleanValues.map((toggleValue) => {
        return (
          <Popover
            position="bottom-start"
            on="hover"
            disabled={toggleValue}
            key={toggleValue}
            trigger={
              <Button appearance="basic" disabled={true}>
                {toggleValue ? 'Disabled Popover' : 'Show Popover'}
              </Button>
            }
            open={false}
            className="w-25"
          >
            <div className="p-6">
              <Text>You have some edits saved in draft state.You can resume editing or discard those changes.</Text>
            </div>
          </Popover>
        );
      })}
    </div>
  );
}
```


#### Components Popover Layering

```jsx
import { Popover, Button, Select } from '@innovaccer/design-system';

() => {
  const options = [
    { label: 'Draft', value: 'draft' },
    { label: 'In Progress', value: 'in_progress' },
    { label: 'Sent', value: 'sent' },
    { label: 'Scheduled', value: 'scheduled' },
    { label: 'Partially Failed', value: 'partially_failed' },
    { label: 'Completely Failed', value: 'completely_failed' },
  ];

  return (
    <div className="mb-9">
      <Popover position="bottom" on="click" trigger={<Button appearance="basic">Open Popover</Button>} open={false}>
        <div className="pb-11 pr-10">
          <Select
            className="p-6"
            width={100}
            popoverWidth={176}
            triggerOptions={{
              placeholder: 'Status',
            }}
          >
            <Select.List>
              {options.map((option, key) => {
                return (
                  <Select.Option key={key} option={{ label: option.label, value: option.value }}>
                    {option.label}
                  </Select.Option>
                );
              })}
            </Select.List>
          </Select>
        </div>
      </Popover>
    </div>
  );
}

```


#### Components Popover Light Popover

```jsx
import { Popover, Button } from '@innovaccer/design-system';

() => (
  <div className="mb-9">
    <Popover position="bottom" on="click" trigger={<Button appearance="basic">Open Popover</Button>} open={false}>
      <div className="p-10" />
    </Popover>
  </div>
)
```


#### Components Popover Popover With Action

```jsx
import { Popover, Button, Text } from '@innovaccer/design-system';

() => (
  <div className="mb-10">
    <Popover
      position="bottom-start"
      on="click"
      trigger={<Button appearance="basic">Open Popover</Button>}
      open={false}
      className="w-25"
    >
      <div className="m-6">
        <Text>You have some edits saved in draft state.You can resume editing or discard those changes.</Text>
        <div className="d-flex">
          <Button className="mt-4" appearance="primary">
            Edit Registry
          </Button>
          <Button className="mt-4 ml-4" appearance="basic">
            Discard Changes
          </Button>
        </div>
      </div>
    </Popover>
  </div>
)
```


#### Components Popover Popover With Input

```jsx
import { Popover, LinkButton, Label, Input, Textarea, Button } from '@innovaccer/design-system';

() => (
  <div className="mb-13">
    <Popover position="bottom-start" on="click" trigger={<LinkButton>Open Popover</LinkButton>} open={false}>
      <div className="m-6">
        <Label required={true} withInput={true}>
          Name
        </Label>
        <Input name="input" required={true} placeholder="Name" />
        <Label className="mt-4" withInput={true}>
          Description
        </Label>
        <Textarea name="Textarea" placeholder="Write a description" />
        <div className="d-flex justify-content-end">
          <Button className="mt-5" appearance="primary">
            Save Filter
          </Button>
        </div>
      </div>
    </Popover>
  </div>
)
```


#### Components Popover Popover With Menu

```jsx
import { Avatar, Button, Popover, Text } from '@innovaccer/design-system';

() => {
  const trigger = (
    <div className="d-flex">
      <Avatar firstName="John" lastName="Doe" />
      <Button className="ml-3" appearance="transparent" icon="arrow_drop_down" iconAlign="right">
        Open Popover
      </Button>
    </div>
  );

  return (
    <div className="mb-12">
      <Popover position="bottom-start" on="click" trigger={trigger} open={false} className="w-25">
        <div className="pt-7 pb-4 pl-7">
          <div className="d-flex pr-7 pb-6">
            <Avatar firstName="John" lastName="Doe" />
            <div className="Option-label">
              <Text className="ml-5">James Donovan</Text>
              <Text className="ml-5" appearance="subtle">
                jdonovan @two.health
              </Text>
            </div>
          </div>
          <div>
            <div className="Option pl-0 pr-4">Account Overview</div>
            <div className="Option pl-0 pr-4">Sign Out</div>
          </div>
        </div>
      </Popover>
    </div>
  );
}
```


#### Components Popover Variants Boundary Element

```jsx
import { Popover, Button, Text } from '@innovaccer/design-system';

/*
// style.css
.custom-boundaryWrapper {
    height: var(--spacing-8);
    border: 1px dashed;
}

*/

() => {
  const ref = React.useRef(null);

  return(
    <div ref={ref} className="overflow-auto p-7 custom-boundaryWrapper">
      <Popover
        position="bottom-start"
        on="click"
        open={true}
        trigger={<Button appearance="basic">Open Popup</Button>}
        boundaryElement={ref}
        closeOnScroll={true}
      >
        <div className='m-6 pr-9'>
          <Text>Popup</Text>
          <Button appearance="primary" className="mt-4">Click</Button>
        </div>
      </Popover>
      <div className="pb-14" />
    </div>
  );
}
```


#### Popover

```jsx
import { Button, Popover, Text } from '@innovaccer/design-system';

() => {
  const positions = [
    'top',
    'top-start',
    'top-end',
    'bottom',
    'bottom-start',
    'bottom-end',
    'left',
    'left-start',
    'left-end',
    'right',
    'right-start',
    'right-end',
    'auto-start',
    'auto',
    'auto-end',
  ];
  const getTrigger = (pos) => <Button appearance="basic">{pos}</Button>;

  return (
    <div className="d-flex flex-wrap">
      {positions.map((pos, ind) => {
        return (
          <div key={ind} className={`mr-13 ml-12 ${ind < 3 ? 'mt-11' : 'mt-5 mb-11'}`}>
            <Popover trigger={getTrigger(pos)} position={pos}>
              <div className="m-6 pr-9">
                <Text>Popup</Text>
                <Button appearance="primary" className="mt-4">
                  Click
                </Button>
              </div>
            </Popover>
          </div>
        );
      })}
    </div>
  );
}
```# ProgressBar



### Code Examples

#### Components Progress Indicators ProgressBar All

```jsx
import { ProgressBar } from '@innovaccer/design-system';

() => {
  const value = 10;
  const max = 100;

  return (
    <div className="w-50">
      <ProgressBar value={value} max={max} />
    </div>
  );
}
```


#### Components Progress Indicators ProgressBar Fifty Percent

```jsx
import { ProgressBar } from '@innovaccer/design-system';

() => <ProgressBar value={50} max={100} />
```


#### ProgressBar

```jsx
import { ProgressBar, Text } from '@innovaccer/design-system';

() => {
  const sizes = ['small', 'regular'];
  return (
    <div className="w-75">
      {sizes.map((ProgressBarSize, ind) => {
        return (
          <div key={ind} className="mb-7">
            <ProgressBar size={ProgressBarSize} value={30} />
            <br />
            <Text weight="strong">{ProgressBarSize.charAt(0).toUpperCase() + ProgressBarSize.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### ProgressBar

```jsx
import { ProgressBar } from '@innovaccer/design-system';

() => {
  const [progress, setProgress] = React.useState(0);
  
  React.useEffect(() => {
    const interval = setInterval(() => {
      setProgress(progress + 25);
    }, 1000);
  });

  return <ProgressBar value={progress} max={100} />;
}
```# ProgressIndicator-Horizontal



### Code Examples

#### Progress Indicator - Horizontal

```jsx
import { SaraSparkle, Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex align-items-center justify-content-center">
      <SaraSparkle size={24} state="listening" className="mr-3" />
      <Text className="shimmer-text">Sara is listening</Text>
    </div>
  );
}
```# ProgressIndicator-Vertical



### Code Examples

#### Progress Indicator - Vertical

```jsx
import { SaraSparkle, Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex align-items-center justify-content-center flex-column">
      <SaraSparkle size={48} state="listening" className="mb-3" />
      <Text className="shimmer-text" size="large">
        Sara is listening
      </Text>
    </div>
  );
}
```# ProgressRing



### Code Examples

#### Components Progress Indicators ProgressRing All

```jsx
import { ProgressRing } from '@innovaccer/design-system';

() => {
  const value = 50;
  const max = 100;

  return <ProgressRing value={value} max={max} />;
}
```


#### ProgressRing

```jsx
import { ProgressRing, Text } from '@innovaccer/design-system';

() => {
  const sizes = ['small', 'regular', 'large'];
  return (
    <div className="d-flex">
      {sizes.map((ProgressRingSize, ind) => {
        return (
          <div key={ind} className="mr-10 d-flex flex-column align-items-center">
            <ProgressRing size={ProgressRingSize} value={30} />
            <br />
            <Text weight="strong">{ProgressRingSize.charAt(0).toUpperCase() + ProgressRingSize.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### ProgressRing

```jsx
import { ProgressRing } from '@innovaccer/design-system';

() => {
  const [progress, setProgress] = React.useState(0);
  
  React.useEffect(() => {
    const interval = setInterval(() => {
      setProgress(progress + 25);
    }, 1000);

    return () => clearInterval(interval)
  });

  return <ProgressRing value={progress} max={100} />;
}
```# Radio

Radio button lets users select one value from a list of mutually exclusive choices.

### Code Examples

#### Components Radio All

```jsx
import { Radio } from '@innovaccer/design-system';

() => {
  const label = 'Radio';

  const name = 'gender';

  const onChangeHandler = (event) => {
    return action(`onChange: ${event.target.value}: ${event.target.checked}`)();
  };

  return <Radio label={label} name={name} value={label} onChange={onChangeHandler} />;
}
```


#### Components Radio RadioGroup Controlled

```jsx
import { ChoiceList } from '@innovaccer/design-system';

() => {
  const label = 'Days';
  const alignmentHorizontal = 'horizontal';
  const days = [
    { label: 'Mon', name: 'days', value: 'mon' },
    { label: 'Tue', name: 'days', value: 'tue' },
    { label: 'Wed', name: 'days', value: 'wed' },
    { label: 'Thu', name: 'days', value: 'thu' },
    { label: 'Fri', name: 'days', value: 'fri' },
    { label: 'Sat', name: 'days', value: 'sat' },
    { label: 'Sun', name: 'days', value: 'sun' },
  ];

  return (
    <>
      <ChoiceList
        selected={['mon', 'wed', 'sat']}
        choices={days}
        title={label}
        alignment={alignmentHorizontal}
        onChange={() => {}}
      />
    </>
  );
}
```


#### Components Radio RadioGroup Horizontal

```jsx
import { ChoiceList } from '@innovaccer/design-system';

() => {
  return (
    <ChoiceList
      alignment="horizontal"
      choices={[
        { label: 'Male', name: 'gender', value: 'Male' },
        { label: 'Female', name: 'gender', value: 'Female' },
        { label: 'Other', name: 'gender', value: 'Other' },
      ]}
      title="Gender"
    />
  );
}
```


#### Components Radio RadioGroup Vertical

```jsx
import { ChoiceList } from '@innovaccer/design-system';

() => {
  return (
    <ChoiceList
      choices={[
        { label: 'Male', name: 'gender', value: 'Male' },
        { label: 'Female', name: 'gender', value: 'Female' },
        { label: 'Other', name: 'gender', value: 'Other' },
      ]}
      title="Gender"
    />
  );
}
```


#### Components Radio Variants Error

```jsx
import { Radio } from '@innovaccer/design-system';

() => <Radio label={'Error label'} name={'Radio'} value={'Radio'} error={true} />
```


#### Components Radio Variants Size

```jsx
import { Radio } from '@innovaccer/design-system';

() => {
  const sizes = ['tiny', 'regular'];

  const name = 'gender';
  return (
    <div className="d-flex w-25 justify-content-between">
      {sizes.map((RadioSize, ind) => {
        return (
          <Radio
            key={ind}
            size={RadioSize}
            label={RadioSize.charAt(0).toUpperCase() + RadioSize.slice(1)}
            name={name}
            value={RadioSize}
          />
        );
      })}
    </div>
  );
}
```


#### Components Radio Variants State

```jsx
import { Radio } from '@innovaccer/design-system';

() => {
  const name = 'state';

  return (
    <div className="d-flex w-25 justify-content-between">
      <Radio label={'Disabled'} name={name} value={'Disabled'} disabled={true} />
      <Radio label={'Enabled'} name={name} value={'Enabled'} disabled={false} />
    </div>
  );
}
```


#### Components Radio Default Checked

```jsx
import { Radio } from '@innovaccer/design-system';

() => (
  <Radio defaultChecked={true} label={'Survey Outreach'} name={'Radio'} value={'Radio'} />
)
```


#### Components Radio Overflow Content

```jsx
import { Radio } from '@innovaccer/design-system';

() => (
  <Radio
    className="w-25"
    label="Share both your healthcare data and some personal information."
    name="options"
    value="Option 1"
  />
)
```


#### Components Radio With Help Text

```jsx
import { Radio } from '@innovaccer/design-system';

() => {
  return (
    <Radio
      label={'Share all your data'}
      value={'accepted'}
      name={'consent'}
      helpText={'This app will have access to both your healthcare data and some personal information.'}
      className="w-50"
    />
  );
}
```# RangeSlider



### Code Examples

#### Components Slider RangeSlider All

```jsx
import { RangeSlider } from '@innovaccer/design-system';

() => {
  const min = 0;
  const max = 10;
  const stepSize = 0.1;
  const labelStepSize = 1;
  const label = 'Slider Label';
  const disabled = false;

  const onChange = (value) => {
    return action(`new value: ${value}`);
  };

  const options = {
    min,
    max,
    stepSize,
    labelStepSize,
    label,
    disabled,
    onChange,
    defaultValue: [2, 4],
  };

  return <RangeSlider className="my-8" {...options} />;
}
```


#### Components Slider RangeSlider Custom Labels

```jsx
import { RangeSlider } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState([2, 4]);

  const onChange = (value) => {
    setValue(value);
  };

  const labelRenderer = (value) => {
    return `${value}%`;
  };

  return (
    <RangeSlider
      min={1}
      max={10}
      value={value}
      stepSize={0.1}
      labelStepSize={1}
      onChange={onChange}
      labelRenderer={labelRenderer}
      className="my-8"
    />
  );
}
```


#### Components Slider RangeSlider Disabled

```jsx
import { RangeSlider } from '@innovaccer/design-system';

() => {
  return (
    <RangeSlider
      className="my-8"
      label="Disabled Slider"
      disabled={true}
      stepSize={0.1}
      labelStepSize={1}
      defaultValue={[2, 4]}
    />
  );
}
```


#### Components Slider RangeSlider Types Controlled Slider

```jsx
import { RangeSlider } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState([2, 4]);

  const onChange = (value) => {
    setValue(value);
  };

  return (
    <RangeSlider
      min={1}
      max={10}
      label='Controlled Slider'
      stepSize={0.1}
      labelStepSize={1}
      value={value}
      onChange={onChange}
      className="my-8"
    />
  );
}
```


#### Components Slider RangeSlider Types Uncontrolled Slider

```jsx
import { RangeSlider } from '@innovaccer/design-system';

() => {
  return (
    <RangeSlider
      min={1}
      max={10}
      label="Uncontrolled Slider"
      stepSize={0.1}
      labelStepSize={1}
      defaultValue={[2, 4]}
      className="my-8"
    />
  );
}
```


#### Components Slider RangeSlider Variants Discrete Slider

```jsx
import { RangeSlider } from '@innovaccer/design-system';

() => {
  return (
    <RangeSlider
      min={1}
      max={10}
      label="Discrete Slider"
      stepSize={1}
      labelStepSize={1}
      defaultValue={[2, 4]}
      className="my-8"
    />
  );
}
```


#### Components Slider RangeSlider Variants Free Slider

```jsx
import { RangeSlider } from '@innovaccer/design-system';

() => {
  return (
    <RangeSlider
      min={1}
      max={10}
      label="Free Slider"
      stepSize={0.1}
      labelStepSize={1}
      defaultValue={[2, 4]}
      className="my-8"
    />
  );
}
```# Row



### Code Examples

#### Components Layout Row

```jsx
import { Row, Column } from '@innovaccer/design-system';

() => {
  return (
    <>
      <Row>
        <Column className="p-6 bg-secondary-lightest border">Row 1</Column>
      </Row>
      <Row className="mt-3">
        <Column className="p-6 bg-secondary-lightest border">Row 2</Column>
      </Row>
      <Row className="mt-3">
        <Column className="p-6 bg-secondary-lightest border">Row 3</Column>
      </Row>
      <Row className="mt-3">
        <Column className="p-6 bg-secondary-lightest border">Row 4</Column>
      </Row>
      <Row className="mt-3">
        <Column className="p-6 bg-secondary-lightest border">Row 5</Column>
      </Row>
    </>
  );
}
```# Sara

Sara, represented by a magic sparkle, is the avatar used for artificial intelligence.

### Code Examples

#### Sara

```jsx
import { Sara } from '@innovaccer/design-system';

() => {
  return <Sara />;
}
```


#### Sara

```jsx
import { Sara } from '@innovaccer/design-system';

() => {
  return <Sara size={100} />;
}
```


#### Sara

```jsx
import { Sara, Text } from '@innovaccer/design-system';

() => {
  return (
    <div>
      <div className="d-flex justify-content-between align-items-center w-75">
        <div className="d-flex flex-column align-items-center text-align-center w-100">
          <Sara />
          <Text appearance="subtle" className="mt-6">
            32
          </Text>
        </div>
        <div className="d-flex flex-column align-items-center text-align-center w-100">
          <Sara size={48} />
          <Text appearance="subtle" className="mt-6">
            48
          </Text>
        </div>
        <div className="d-flex flex-column align-items-center text-align-center w-100">
          <Sara size={64} />
          <Text appearance="subtle" className="mt-6">
            64
          </Text>
        </div>
      </div>
    </div>
  );
}
```


#### Sara

```jsx
import { Sara, Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex w-75">
      <div className="d-flex flex-column align-items-center text-align-center w-100">
        <Sara />
        <Text appearance="subtle" className="mt-6">
          Default
        </Text>
      </div>
      <div className="d-flex flex-column align-items-center text-align-center w-100">
        <Sara state="resting" />
        <Text appearance="subtle" className="mt-6">
          Resting
        </Text>
      </div>
    </div>
  );
}
```# SaraSparkle



### Code Examples

#### SaraSparkle

```jsx
import { SaraSparkle } from '@innovaccer/design-system';

() => {
  return <SaraSparkle />;
}
```


#### SaraSparkle

```jsx
import { SaraSparkle } from '@innovaccer/design-system';

() => {
  return <SaraSparkle size={100} />;
}
```


#### SaraSparkle

```jsx
import { SaraSparkle, Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex vw-50">
      <div className="d-flex flex-column align-items-center text-align-center w-100">
        <SaraSparkle size={16} />
        <Text appearance="subtle" className="mt-6">
          16
        </Text>
      </div>
      <div className="d-flex align-items-center flex-column text-align-center w-100">
        <SaraSparkle size={24} />
        <Text appearance="subtle" className="mt-6">
          24
        </Text>
      </div>
      <div className="d-flex align-items-center flex-column text-align-center w-100">
        <SaraSparkle size={32} />
        <Text appearance="subtle" className="mt-6">
          32
        </Text>
      </div>
      <div className="d-flex align-items-center flex-column text-align-center w-100">
        <SaraSparkle size={48} />
        <Text appearance="subtle" className="mt-6">
          48
        </Text>
      </div>
    </div>
  );
}
```


#### SaraSparkle

```jsx
import { SaraSparkle, Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex vw-50">
      <div className="d-flex flex-column align-items-center text-align-center w-100">
        <SaraSparkle size={64} />
        <Text appearance="subtle" className="mt-6">
          Default
        </Text>
      </div>
      <div className="d-flex align-items-center flex-column text-align-center w-100">
        <SaraSparkle state="listening" size={64} />
        <Text appearance="subtle" className="mt-6">
          Listening
        </Text>
      </div>
      <div className="d-flex align-items-center flex-column text-align-center w-100">
        <SaraSparkle state="short-processing" size={64} />
        <Text appearance="subtle" className="mt-6">
          Short Processing
        </Text>
      </div>
      <div className="d-flex align-items-center flex-column text-align-center w-100">
        <SaraSparkle state="long-processing" size={64} />
        <Text appearance="subtle" className="mt-6">
          Long Processing
        </Text>
      </div>
    </div>
  );
}
```# Select

Select offers multiple choices in a compact way.

### Code Examples

#### Select

```jsx
import { Select } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril', value: 'Lisinopril' },
    { label: 'Simvastatin', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
    { label: 'Omeprazole', value: 'Omeprazole' },
    { label: 'Diazepam', value: 'Diazepam' },
    { label: 'Levothyroxine', value: 'Levothyroxine' },
  ];
  

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  return (
    <Select onSelect={onSelectHandler} >
        <Select.List>
          {medicineList.map((item, key) => {
            return (
              <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                {item.label}
              </Select.Option>
            );
          })}
        </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Select, Text } from '@innovaccer/design-system';

() => {
    const [medicineList, setMedicineList] = React.useState([
      { label: 'Acetaminophen', value: 'Acetaminophen' },
      { label: 'Ibuprofen', value: 'Ibuprofen' },
      { label: 'Penicillin G', value: 'Penicillin G' },
      { label: 'Penbutolol', value: 'Penbutolol' },
      { label: 'Aminophenol', value: 'Aminophenol' },
      { label: 'Vancomycin', value: 'Vancomycin' },
      { label: 'Aspirin', value: 'Aspirin' },
      { label: 'Paracetamol', value: 'Paracetamol' },
      { label: 'Lisinopril', value: 'Lisinopril' },
      { label: 'Simvastatin', value: 'Simvastatin' },
      { label: 'Amoxicillin', value: 'Amoxicillin' },
      { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
      { label: 'Metformin', value: 'Metformin' },
    ]);
  
    const [searchTerm, setSearchTerm] = React.useState('');
    const [filteredMedicines, setFilteredMedicines] = React.useState(medicineList);
    const [showAddOption, setShowAddOption] = React.useState(false);
    const selectRef = React.useRef(null);
  
    React.useEffect(() => {
      if (searchTerm.trim() === '') {
        setFilteredMedicines(medicineList);
        setShowAddOption(false);
      } else {
        const newList = medicineList.filter((medicine) =>
          medicine.label.toLowerCase().includes(searchTerm.toLowerCase())
        );

        const searchTearmFilter = medicineList.filter((medicine) =>
          medicine.label.toLowerCase() === searchTerm.toLowerCase()
        );
  
        setFilteredMedicines(newList);
        setShowAddOption(searchTearmFilter.length === 0);
      }
    }, [searchTerm, medicineList]);
  
    const onChangeHandler = (value) => {
      setSearchTerm(value);
    };
  
    const onClearHandler = () => {
      setSearchTerm('');
    };
  
    const onSelectHandler = (selectedOption) => {
      console.log('selectedOption', selectedOption);
    };
  
    const onAddMedicine = () => {
      const newMedicine = { label: searchTerm, value: searchTerm };
      setMedicineList((prevList) => [...prevList, newMedicine]);
      selectRef.current.setFocusFirstItem();
      setSearchTerm('');
    };
  
    return (
      <Select ref={selectRef} onSelect={onSelectHandler}>
        <Select.SearchInput
          value={searchTerm}
          placeholder="Search"
          onChange={onChangeHandler}
          onClear={onClearHandler}
        />
        <Select.List>
          {filteredMedicines.map((item, key) => (
            <Select.Option key={key} option={item}>
              {item.label}
            </Select.Option>
          ))}
          {showAddOption && (
            <Select.Option onClick={onAddMedicine} option={{ label: 'Add new medicine', value: 'add_new' }}> 
              <Text color="primary"> Add "{searchTerm}" </Text>
            </Select.Option>
          )}
        </Select.List>
      </Select>
    );
  }
```


#### Select

```jsx
import { Select, Button, AIIconButton, Text } from '@innovaccer/design-system';

() => {
    /**
   *
   *  .Button-primary--active  {
   *     background-color: var(--primary-darker);
   *  }
   *
   *  .AIButton-secondary--active {
   *    background-color: var(--secondary-dark);
   *    color: var(--secondary-dark)  !important;
   *  }
   *
   *  .Button-secondary--active {
   *     background-color: var(--secondary-dark);
   *  }
   */

  const [isStatusSelectOpen, setStatusSelectOpen] = React.useState(false);
  const [isRecordSelectOpen, setRecordSelectOpen] = React.useState(false);
  const [isOverviewSelectOpen, setOverviewSelectOpen] = React.useState(false);
  const [selectedDevelopmentStatus, setSelectedDevelopmentStatus] = React.useState({
    label: 'Development',
    value: 'Development',
  });

  const statusOptions = [
    { label: 'Published', value: 'Published' },
    { label: 'Finalized for publishing', value: 'Finalized for publishing' },
    { label: 'Signed', value: 'Signed' },
  ];

  const recordOptions = [
    { label: 'L1.xyz_table.sample_record', value: 'L1.sample_record', subInfo: 'Probability Score: 88%' },
    { label: 'L1.xyz_table.last_name', value: 'L1.last_name', subInfo: 'Probability Score: 61%' },
  ];

  const overviewOptions = [
    { label: 'Development', value: 'Development' },
    { label: 'Finalized', value: 'Finalized' },
  ];

  const onStatusSelect = (selectedOption) => {
    console.log('selectedOption', selectedOption);
    setStatusSelectOpen(false);
  };

  const onRecordSelect = (selectedOption) => {
    console.log('selectedOption', selectedOption);
    setRecordSelectOpen(false);
  };

  const onOverviewSelect = (selectedOption) => {
    console.log('selectedOption', selectedOption);
    setOverviewSelectOpen(false);
    setSelectedDevelopmentStatus(selectedOption);
  };

  const onToggleStatusSelect = (isOpen) => {
    setStatusSelectOpen(isOpen);
  };

  const onToggleRecordSelect = (isOpen) => {
    setRecordSelectOpen(isOpen);
  };

  const onToggleOverviewSelect = (isOpen) => {
    setOverviewSelectOpen(isOpen);
  };

  const getStatusLabel = () => {
    return selectedDevelopmentStatus ? selectedDevelopmentStatus.label : 'Select';
  };

  return (
    <div className="d-flex justify-content-around">
      <Select
        onSelect={onStatusSelect}
        onToggle={onToggleStatusSelect}
        trigger={
          <Button
            appearance="primary"
            className={isStatusSelectOpen ? 'Button-primary--active' : ''}
            icon={isStatusSelectOpen ? 'expand_less' : 'expand_more'}
            iconAlign="right"
          >
            Updated status for P1
          </Button>
        }
      >
        <Select.List>
          {statusOptions.map((item, key) => (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Select.Option>
          ))}
        </Select.List>
      </Select>

      <Select
        popoverWidth="var(--spacing-9)"
        onSelect={onRecordSelect}
        onToggle={onToggleRecordSelect}
        trigger={
          <AIIconButton
            className={isRecordSelectOpen ? 'AIButton-secondary--active' : ''}
            icon="import_contacts"
            type="button"
          />
        }
      >
        <Select.List>
          <Text className="d-flex ml-6 mt-5 mr-5 mb-4" size="small" appearance="subtle">
            Mapping suggestions
          </Text>
          {recordOptions.map((item, key) => (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              <div className="d-flex flex-column">
                <Text>{item.label}</Text>
                <Text size="small" appearance="subtle">
                  {item.subInfo}
                </Text>
              </div>
            </Select.Option>
          ))}
        </Select.List>
      </Select>

      <Select
        onSelect={onOverviewSelect}
        onToggle={onToggleOverviewSelect}
        value={selectedDevelopmentStatus}
        trigger={
          <Button
            appearance="transparent"
            className={isOverviewSelectOpen ? 'Button-secondary--active' : ''}
            icon={isOverviewSelectOpen ? 'expand_less' : 'expand_more'}
            iconAlign="right"
          >
            {getStatusLabel()}
          </Button>
        }
      >
        <Select.List>
          {overviewOptions.map((item, key) => (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Select.Option>
          ))}
        </Select.List>
      </Select>
    </div>
  );
}
```


#### Select

```jsx
import { Select } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril', value: 'Lisinopril' },
    { label: 'Simvastatin', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
    { label: 'Omeprazole', value: 'Omeprazole' },
    { label: 'Diazepam', value: 'Diazepam' },
    { label: 'Levothyroxine', value: 'Levothyroxine' },
  ];
  

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  return (
    <Select triggerOptions={{ disabled: true }} onSelect={onSelectHandler} >
        <Select.List>
          {medicineList.map((item, key) => {
            return (
              <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                {item.label}
              </Select.Option>
            );
          })}
        </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Select, Button } from '@innovaccer/design-system';

() => {
  const medicineList = [];
  const [ searchTerm , setSearchTerm ] = React.useState('');

  const onChangeHandler = (value) => {
    setSearchTerm(value)
  }

  const onClearHandler = () => {
    setSearchTerm('')
  }
  
  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  return (
    <Select onSelect={onSelectHandler}>
      <Select.SearchInput
        value={searchTerm}
        placeholder='Search'
        onChange={onChangeHandler}
        onClear={onClearHandler}
      ></Select.SearchInput>
      {medicineList.length === 0 ? (
        <Select.EmptyTemplate
          description="We couldn't load the data, try reloading."
          title="Failed to fetch data">
        <Button onClick={function(){}} size="tiny" aria-label="Reload" icon="refresh" iconAlign="left">Reload</Button>
        </Select.EmptyTemplate>
      ) : (
      <Select.List>
          {medicineList.map((item, key) => (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Select.Option>
          ))}
      </Select.List>
      )}
    </Select>
  );
}
```


#### Select

```jsx
import { Label, Select } from '@innovaccer/design-system';

() => {
  const areaCode = [
    { label: 'Alabama (205)', value: 'Alabama (205)' },
    { label: 'Alabama (251)', value: 'Alabama (251)' },
    { label: 'Alabama (256)', value: 'Alabama (256)' },
    { label: 'Alabama (334)', value: 'Alabama (334)' },
    { label: 'Alabama (938)', value: 'Alabama (938)' },
    { label: 'Arizona (520)', value: 'Arizona (520)' },
    { label: 'California (209)', value: 'California (209)' },
    { label: 'California (408)', value: 'California (408)' },
    { label: 'Colorado (719)', value: 'Colorado (719)' },
    { label: 'Connecticut (860)', value: 'Connecticut (860)' },
  ];

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  return (
    <div className="w-25">
      <Label withInput={true}>Area code</Label>
      <Select onSelect={onSelectHandler}>
        <Select.List>
          {areaCode.map((item, key) => {
            return (
              <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                {item.label}
              </Select.Option>
            );
          })}
        </Select.List>
      </Select>
    </div>
  );
};
```


#### Select

```jsx
import { Select, Spinner } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril', value: 'Lisinopril' },
    { label: 'Simvastatin', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
    { label: 'Omeprazole', value: 'Omeprazole' },
    { label: 'Diazepam', value: 'Diazepam' },
    { label: 'Levothyroxine', value: 'Levothyroxine' },
  ];

  const [loading, setLoading] = React.useState(true);
  const [searchTerm, setSearchTerm] = React.useState('');
  const [filteredMedicines, setFilteredMedicines] = React.useState(medicineList);
  const [error, setError] = React.useState(false);

  const fetchOptions = (searchTerm) => {
    const searchedOptions =
      searchTerm.trim() === ''
        ? medicineList
        : medicineList.filter((medicine) => medicine.label.toLowerCase().includes(searchTerm.toLowerCase()));
    return new Promise((resolve) => {
      setTimeout(() => {
        resolve({ option: searchedOptions });
      }, 1000);
    });
  };

  React.useEffect(() => {
    setLoading(true);
    fetchOptions(searchTerm).then((res) => {
      const { option } = res;
      setFilteredMedicines(option);
      setError(option.length === 0);
      setLoading(false);
    });
  }, [searchTerm]);

  const onChangeHandler = (value) => setSearchTerm(value);
  const onClearHandler = () => setSearchTerm('');
  const onSelectHandler = (selectedOption) => console.log('selectedOption', selectedOption);

  return (
    <Select onSelect={onSelectHandler}>
      <Select.SearchInput
        value={searchTerm}
        placeholder="Search"
        onChange={onChangeHandler}
        onClear={onClearHandler}
      />
      {loading ? (
        <Select.EmptyTemplate>
          <Spinner />
        </Select.EmptyTemplate>
      ) : error ? (
        <Select.EmptyTemplate
          description="Try modifying your search to find what you are looking for."
          size="small"
          title="No results found"
        />
      ) : (
        <Select.List>
          {filteredMedicines.map((item, key) => (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Select.Option>
          ))}
        </Select.List>
      )}
    </Select>
  );
}
```


#### Select

```jsx
import { Select } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril', value: 'Lisinopril' },
    { label: 'Simvastatin', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
    { label: 'Omeprazole', value: 'Omeprazole' },
    { label: 'Diazepam', value: 'Diazepam' },
    { label: 'Levothyroxine', value: 'Levothyroxine' },
  ];
  

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  const setLableHandler = (count) => {
    if (count > 2) {
      return `${count} Medicines`;
    }
  }

  return (
    <Select triggerOptions={{ setLabel: setLableHandler }} onSelect={onSelectHandler} multiSelect={true} >
        <Select.List>
          {medicineList.map((item, key) => {
            return (
              <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                {item.label}
              </Select.Option>
            );
          })}
        </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Select } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril', value: 'Lisinopril' },
    { label: 'Simvastatin', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
    { label: 'Omeprazole', value: 'Omeprazole' },
    { label: 'Diazepam', value: 'Diazepam' },
    { label: 'Levothyroxine', value: 'Levothyroxine' },
  ];
  

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  const setLableHandler = (count) => {
    if (count > 2) {
      return `${count} Medicines`;
    }
  }

  return (    
  <Select
    triggerOptions={{ setLabel: setLableHandler }}
    value={[
      { label: 'Aspirin', value: 'Aspirin' },
      { label: 'Paracetamol', value: 'Paracetamol' }
    ]}
    onSelect={onSelectHandler}
    multiSelect={true}
  >
        <Select.List>
          {medicineList.map((item, key) => {
            return (
              <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                {item.label}
              </Select.Option>
            );
          })}
        </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Select, Text } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin', group: 'Painkillers' },
    { label: 'Paracetamol', value: 'Paracetamol', group: 'Painkillers' },
    { label: 'Lisinopril', value: 'Lisinopril', group: 'Hypertension' },
    { label: 'Simvastatin', value: 'Simvastatin', group: 'Antibiotics' },
    { label: 'Amoxicillin', value: 'Amoxicillin', group: 'Antibiotics' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin', group: 'Antibiotics' },
    { label: 'Omeprazole', value: 'Omeprazole', group: 'Painkillers' },
    { label: 'Diazepam', value: 'Diazepam', group: 'Antibiotics' },
    { label: 'Levothyroxine', value: 'Levothyroxine', group: 'Antibiotics' },
    { label: 'Ibuprofen', value: 'Ibuprofen', group: 'Painkillers' },
    { label: 'Prednisone', value: 'Prednisone', group: 'Painkillers' },
    { label: 'Metoprolol', value: 'Metoprolol', group: 'Hypertension' },
  ];

  const [selectedOptions, setSelectedOptions] = React.useState([]);
  const selectRef = React.useRef(null);

  const handleSelect = (selectedOption) => {
    console.log('selectedOption', selectedOption);
    selectRef.current.setFocusFirstItem();
    setSelectedOptions(selectedOption);
  };

  const onClearHandler = () => {
    setSelectedOptions([]);
  };

  const groupedMedicine = medicineList.reduce((acc, item) => {
    const groupKey = selectedOptions.find((opt) => opt.value === item.value) ? 'Selected Items' : item.group;
    if (!acc[groupKey]) {
      acc[groupKey] = [];
    }
    acc[groupKey].push(item);
    return acc;
  }, {});

  return (
    <Select
      ref={selectRef}
      onSelect={handleSelect}
      value={selectedOptions}
      multiSelect={true}
      triggerOptions={{ onClear: onClearHandler }}
    >
      <Select.List>
        {selectedOptions.length > 0 && (
          <React.Fragment>
            <Text className="d-flex ml-6 mt-5 mr-5 mb-4" size="small" appearance="subtle">
              Selected Items
            </Text>
            {selectedOptions.map((option) => (
              <Select.Option key={option.value} option={option}>
                {option.label}
              </Select.Option>
            ))}
          </React.Fragment>
        )}
        {Object.keys(groupedMedicine).map(
          (group) =>
            group !== 'Selected Items' &&
            groupedMedicine[group].length > 0 && (
              <React.Fragment key={group}>
                <Text
                  className="d-flex ml-6 mt-5 mr-5 mb-4"
                  size="small"
                  appearance={'subtle'}
                >
                  {group}
                </Text>
                {groupedMedicine[group].map((item) => (
                  <Select.Option key={item.value} option={{ label: item.label, value: item.value }}>
                    {item.label}
                  </Select.Option>
                ))}
              </React.Fragment>
            )
        )}
      </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Select, Button } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril', value: 'Lisinopril' },
    { label: 'Simvastatin', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
    { label: 'Omeprazole', value: 'Omeprazole' },
    { label: 'Diazepam', value: 'Diazepam' },
    { label: 'Levothyroxine', value: 'Levothyroxine' },
  ];

  const selectRef = React.useRef(null);
  const [selectedOptions, setSelectedOptions] = React.useState([]);
  const [previousSelectedOptions, setPreviousSelectedOptions] = React.useState([]);
  const [isDisabled, setIsDisabled] = React.useState(true);

  const handleSelect = (selectedOption) => {
    setIsDisabled(false);
    console.log('selectedOption', selectedOption);
    setSelectedOptions(selectedOption);
  };

  const onClearHandler = () => {
    setSelectedOptions([]);
    setPreviousSelectedOptions([]);
  };

  const onApplyOptions = () => {
    console.log('onApply button called');
    selectRef.current.setOpen(false);
    setPreviousSelectedOptions(selectedOptions);
  };

  const onCancelOptions = () => {
    console.log('onApply button called');
    selectRef.current.setOpen(false);
    setSelectedOptions(previousSelectedOptions);
  };

  const onOutsideClickHandler = () => {
    setSelectedOptions(previousSelectedOptions);
  };

  React.useEffect(() => {
    setSelectedOptions(previousSelectedOptions);
  }, [previousSelectedOptions]);

  return (
    <Select
      ref={selectRef}
      onOutsideClick={onOutsideClickHandler}
      onSelect={handleSelect}
      value={selectedOptions}
      multiSelect={true}
      triggerOptions={{ onClear: onClearHandler }}
    >
      <Select.List>
        {medicineList.map((item, key) => {
          return (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Select.Option>
          );
        })}
      </Select.List>
      <Select.Footer>
        <Button
          size={'tiny'}
          className="mr-4"
          appearance={'basic'}
          onClick={onCancelOptions}
          data-test="DesignSystem-Select-CancelButton"
          type="button"
        >
          Cancel
        </Button>
        <Button
          appearance={'primary'}
          size={'tiny'}
          onClick={onApplyOptions}
          data-test="DesignSystem-Select-ApplyButton"
          type="button"
          disabled={isDisabled}
        >
          Apply
        </Button>
      </Select.Footer>
    </Select>
  );
}
```


#### Select

```jsx
import { Select, Text } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin', group: 'Painkillers' },
    { label: 'Paracetamol', value: 'Paracetamol', group: 'Painkillers' },
    { label: 'Lisinopril', value: 'Lisinopril', group: 'Hypertension' },
    { label: 'Simvastatin', value: 'Simvastatin', group: 'Antibiotics' },
    { label: 'Amoxicillin', value: 'Amoxicillin', group: 'Antibiotics' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin', group: 'Antibiotics' },
    { label: 'Omeprazole', value: 'Omeprazole', group: 'Painkillers' },
    { label: 'Diazepam', value: 'Diazepam', group: 'Antibiotics' },
    { label: 'Levothyroxine', value: 'Levothyroxine', group: 'Antibiotics' },
    { label: 'Ibuprofen', value: 'Ibuprofen', group: 'Painkillers' },
    { label: 'Prednisone', value: 'Prednisone', group: 'Painkillers' },
    { label: 'Metoprolol', value: 'Metoprolol', group: 'Hypertension' },
  ];

  const [selectedOptions, setSelectedOptions] = React.useState([]);

  const groupedMedicine = medicineList.reduce((acc, item) => {
    const groupKey = item.group;
    if (!acc[groupKey]) {
      acc[groupKey] = [];
    }
    acc[groupKey].push(item);
    return acc;
  }, {});

  const handleSelect = (selectedOption) => {
    console.log('selectedOption', selectedOption);
    setSelectedOptions(selectedOption);
  };

  const onClearHandler = () => {
    setSelectedOptions([]);
  };

  return (
    <Select onSelect={handleSelect} value={selectedOptions} multiSelect={true} triggerOptions={{ onClear: onClearHandler }}>
      <Select.List>
        {Object.keys(groupedMedicine).map((group) => (
          <React.Fragment key={group}>
            <Text
              className="d-flex ml-6 mt-5 mr-5 mb-4"
              size="small"
              appearance={'subtle'}
            >
              {group}
            </Text>
            {groupedMedicine[group].map((item) => (
              <Select.Option key={item.value} option={{ label: item.label, value: item.value }}>
                {item.label}
              </Select.Option>
            ))}
          </React.Fragment>
        ))}
      </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Select } from '@innovaccer/design-system';

() => {
    const medicineList = [
        { label: 'Aspirin', value: 'Aspirin' },
        { label: 'Paracetamol', value: 'Paracetamol' },
        { label: 'Lisinopril', value: 'Lisinopril' },
        { label: 'Simvastatin', value: 'Simvastatin' },
        { label: 'Amoxicillin', value: 'Amoxicillin' },
        { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
        { label: 'Metformin', value: 'Metformin' },
        { label: 'Omeprazole', value: 'Omeprazole' },
        { label: 'Diazepam', value: 'Diazepam' },
        { label: 'Levothyroxine', value: 'Levothyroxine' },
    ];

    const [selectedValue, setSelectedValue] = React.useState([]);
    const [checkedState, setCheckedState] = React.useState('unchecked');

    const onSelectHandler = (selectedOption) => {
        console.log('selectedOption', selectedOption);
        setSelectedValue(selectedOption);
    };

    const onClickHandler = (selectedOption) => {
        console.log(selectedOption, 'onClickHandler');
        if(checkedState === 'checked'){
            setCheckedState('unchecked');
            setSelectedValue([]);
        } else {
            setCheckedState('checked');
            setSelectedValue(medicineList);
        }
    }

    const onClearHandler = () => {
        setCheckedState('unchecked');
        setSelectedValue([]);
    }
    
    React.useEffect(() => {
        if(selectedValue.length === medicineList.length ){
            setCheckedState('checked')
        } else if(selectedValue.length === 0){
            setCheckedState('unchecked')
        } else {
            setCheckedState('indeterminate')
        }
        console.log('Selected Value Changed:', selectedValue);
    }, [checkedState, selectedValue]);

    return (
        <Select 
        onSelect={onSelectHandler} 
        value={selectedValue} 
        multiSelect={true} 
        triggerOptions={{ onClear: onClearHandler }}
        >
            <Select.List>
                <Select.Option checkedState={checkedState} onClick={onClickHandler} option={{ label: 'SelectAll', value: 'SelectAll' }}>
                    Select All
                </Select.Option>
            {medicineList.map((item, key) => {
                return (
                <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                    {item.label}
                </Select.Option>
                );
            })}
            </Select.List>
        </Select>
    );
}
```


#### Select

```jsx
import { Select, Button } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril', value: 'Lisinopril' },
    { label: 'Simvastatin', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
    { label: 'Omeprazole', value: 'Omeprazole' },
    { label: 'Diazepam', value: 'Diazepam' },
    { label: 'Levothyroxine', value: 'Levothyroxine' },
  ];

  const selectRef = React.useRef(null);
  const [selectedOptions, setSelectedOptions] = React.useState([]);
  const [previousSelectedOptions, setPreviousSelectedOptions] = React.useState([]);
  const [checkedState, setCheckedState] = React.useState('unchecked');
  const [isDisabled, setIsDisabled] = React.useState(true);

  const handleSelect = (selectedOption) => {
    setIsDisabled(false);
    console.log('selectedOption', selectedOption);
    setSelectedOptions(selectedOption);
  };

  const handleSelectAllClick = (selectedOption) => {
    setIsDisabled(false);
    console.log(selectedOption, 'handleSelectAllClick');
    if (checkedState === 'checked') {
      setCheckedState('unchecked');
      setSelectedOptions([]);
    } else {
      setCheckedState('checked');
      setSelectedOptions(medicineList);
    }
  };

  const onClearHandler = () => {
    setCheckedState('unchecked');
    setSelectedOptions([]);
    setPreviousSelectedOptions([]);
  };

  const onApplyOptions = () => {
    console.log('onApply button called');
    selectRef.current.setOpen(false);
    setPreviousSelectedOptions(selectedOptions);
  };

  const onCancelOptions = () => {
    console.log('onCancel button called');
    selectRef.current.setOpen(false);
    setSelectedOptions(previousSelectedOptions);
  };

  const onOutsideClickHandler = () => {
    setSelectedOptions(previousSelectedOptions);
  };

  React.useEffect(() => {
    setSelectedOptions(previousSelectedOptions);
  }, [previousSelectedOptions]);

  React.useEffect(() => {
    if (selectedOptions.length === medicineList.length) {
      setCheckedState('checked');
    } else if (selectedOptions.length === 0) {
      setCheckedState('unchecked');
    } else {
      setCheckedState('indeterminate');
    }
  }, [checkedState, selectedOptions]);

  return (
    <Select
      ref={selectRef}
      onOutsideClick={onOutsideClickHandler}
      onSelect={handleSelect}
      value={selectedOptions}
      multiSelect={true}
      triggerOptions={{ onClear: onClearHandler }}
    >
      <Select.List>
        <Select.Option
          checkedState={checkedState}
          onClick={handleSelectAllClick}
          option={{ label: 'SelectAll', value: 'SelectAll' }}
        >
          Select All
        </Select.Option>
        {medicineList.map((item, key) => {
          return (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Select.Option>
          );
        })}
      </Select.List>
      <Select.Footer>
        <Button
          size={'tiny'}
          className="mr-4"
          appearance={'basic'}
          onClick={onCancelOptions}
          data-test="DesignSystem-Select-CancelButton"
          type="button"
        >
          Cancel
        </Button>
        <Button
          appearance={'primary'}
          size={'tiny'}
          onClick={onApplyOptions}
          data-test="DesignSystem-Select-ApplyButton"
          type="button"
          disabled={isDisabled}
        >
          Apply
        </Button>
      </Select.Footer>
    </Select>
  );
}
```


#### Select

```jsx
import { Select, Icon, Text } from '@innovaccer/design-system';

() => {

  const options = [
    { icon: 'more_horiz', label: 'Not yet helped', value: 'not_yet_helped' },
    { icon: 'add', label: 'Eligible', value: 'eligible' },
    { icon: 'horizontal_rule', label: 'Not Eligible', value: 'not_eligible' },
    { icon: 'check', label: 'Got help', value: 'got_help' },
    { icon: 'cancel', label: 'Denied', value: 'denied' },
    { icon: 'info', label: 'Pending', value: 'info_pending' },
    { icon: 'priority_high', label: 'Urgent Needed', value: 'urgent_assistance' },
    { icon: 'history', label: 'History', value: 'prev_helped' },
  ];
  
  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  return (
    <Select onSelect={onSelectHandler} >
        <Select.List>
          {options.map((item, key) => {
            return (
              <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              <div className="d-flex align-items-center">
                <Icon
                className="mr-4"
                name={item.icon}
                />
                <Text> {item.label} </Text>
              </div>
              </Select.Option>
            );
          })}
        </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Select, Text } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Smith, John', subInfo: 'Patient', value: 'Smith_John' },
    { label: 'Jones, Emily', subInfo: 'Primary Care Physician', value: 'Jones_Emily' },
    { label: 'Davis, Michael', subInfo: 'Care Manager', value: 'Davis_Michael' },
    { label: 'Taylor, Jessica', subInfo: 'Patient', value: 'Taylor_Jessica' },
    { label: 'Miller, Robert', subInfo: 'Primary Care Physician', value: 'Miller_Robert' },
    { label: 'Clark, Ashley', subInfo: 'Care Manager', value: 'Clark_Ashley' },
    { label: 'Baker, Christopher', subInfo: 'Patient', value: 'Baker_Christopher' },
    { label: 'Ward, Kimberly', subInfo: 'Primary Care Physician', value: 'Ward_Kimberly' }
  ]

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  return (
    <Select onSelect={onSelectHandler}>
        <Select.List>
          {medicineList.map((item, key) => {
            return (
              <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              <div className='d-flex flex-column'>
                <Text>{item.label}</Text>
                <Text size="small" appearance="subtle">
                {item.subInfo}
                </Text>
              </div>
              </Select.Option>
            );
          })}
        </Select.List>
    </Select>
  );

}
```


#### Select

```jsx
import { Tooltip, Select, Text } from '@innovaccer/design-system';

() => {

  /*
    .Select-Option-label {
      max-width: var(--spacing-7);
    }
  */
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril Anasthesia', value: 'Lisinopril' },
    { label: 'Simvastatin Anasthesia', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
    { label: 'Omeprazole', value: 'Omeprazole' },
    { label: 'Diazepam', value: 'Diazepam' },
    { label: 'Levothyroxine', value: 'Levothyroxine' },
  ];

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  const SelectItem = ({ item }) => {
    const elementRef = React.useRef(null);
    const [showTooltip, setShowTooltip] = React.useState(false);

    return (
      <Tooltip showOnTruncation={true} tooltip={item.label} elementRef={elementRef} open={showTooltip}>
        <Select.Option
          option={{ label: item.label, value: item.value }}
          onFocus={() => {
            setShowTooltip(true);
          }}
          onBlur={() => {
            setShowTooltip(false);
          }}
        >
          <Text ref={elementRef} className="ellipsis--noWrap d-block w-100 Select-Option-label">
            {item.label}
          </Text>
        </Select.Option>
      </Tooltip>
    );
  };

  return (
    <Select onSelect={onSelectHandler}>
      <Select.List>
        {medicineList.map((item, key) => {
          return <SelectItem item={item} key={key} />;
        })}
      </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Label, Select } from '@innovaccer/design-system';

() => {
  const areaCode = [
    { label: 'Alabama (205)', value: 'Alabama (205)' },
    { label: 'Alabama (251)', value: 'Alabama (251)' },
    { label: 'Alabama (256)', value: 'Alabama (256)' },
    { label: 'Alabama (334)', value: 'Alabama (334)' },
    { label: 'Alabama (938)', value: 'Alabama (938)' },
    { label: 'Arizona (520)', value: 'Arizona (520)' },
    { label: 'California (209)', value: 'California (209)' },
    { label: 'California (408)', value: 'California (408)' },
    { label: 'Colorado (719)', value: 'Colorado (719)' },
    { label: 'Connecticut (860)', value: 'Connecticut (860)' },
  ];

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  return (
    <div className="w-25">
      <Label withInput={true}>Area code</Label>
      <Select 
        width="var(--spacing-9)" 
        onSelect={onSelectHandler} 
        value={{ label: 'Alabama (205)', value: 'Alabama (205)' }}
      >
        <Select.List>
          {areaCode.map((item, key) => {
            return (
              <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                {item.label}
              </Select.Option>
            );
          })}
        </Select.List>
      </Select>
    </div>
  );
}
```


#### Select

```jsx
import { Label, Select, HelpText } from '@innovaccer/design-system';

() => {
  const areaCode = [
    { label: 'Alabama (205)', value: 'Alabama (205)' },
    { label: 'Alabama (251)', value: 'Alabama (251)' },
    { label: 'Alabama (256)', value: 'Alabama (256)' },
    { label: 'Alabama (334)', value: 'Alabama (334)' },
    { label: 'Alabama (938)', value: 'Alabama (938)' },
    { label: 'Arizona (520)', value: 'Arizona (520)' },
    { label: 'California (209)', value: 'California (209)' },
    { label: 'California (408)', value: 'California (408)' },
    { label: 'Colorado (719)', value: 'Colorado (719)' },
    { label: 'Connecticut (860)', value: 'Connecticut (860)' },
  ];

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  return (
    <div className="w-25">
      <Label withInput={true}>Area code</Label>
      <Select width="var(--spacing-9)" onSelect={onSelectHandler}>
        <Select.List>
          {areaCode.map((item, key) => {
            return (
              <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                {item.label}
              </Select.Option>
            );
          })}
        </Select.List>
      </Select>
      <HelpText message="If the number with this code is not available, we will use the next best match" />
    </div>
  );
}
```


#### Select

```jsx
import { Select } from '@innovaccer/design-system';

() => {
  const stateAbbreviations = [
    { label: 'Alabama', value: 'AL' },
    { label: 'Alaska', value: 'AK' },
    { label: 'Arizona', value: 'AZ' },
    { label: 'Arkansas', value: 'AR' },
    { label: 'California', value: 'CA' },
    { label: 'Connecticut', value: 'CT' },
    { label: 'Delaware', value: 'DE' },
    { label: 'Florida', value: 'FL' },
    { label: 'Georgia', value: 'GA' },
    { label: 'Hawaii', value: 'HI' },
    { label: 'Idaho', value: 'ID' },
    { label: 'Illinois', value: 'IL' },
  ];

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };


  return (
    <Select triggerOptions={{ icon: 'location_on', placeholder: 'Select state' }} onSelect={onSelectHandler}>
      <Select.List>
        {stateAbbreviations.map((item, key) => {
          return (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Select.Option>
          );
        })}
      </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Row, Column, Label, Select } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril', value: 'Lisinopril' },
    { label: 'Simvastatin', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
    { label: 'Omeprazole', value: 'Omeprazole' },
    { label: 'Diazepam', value: 'Diazepam' },
    { label: 'Levothyroxine', value: 'Levothyroxine' },
  ];

  const list = [
    { label: 'Small', value: 'small' },
    { label: 'Regular', value: 'regular' },
  ];

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };

  return (
    <Row>
      {list.map((size, key) => {
        return (
          <Column key={key} size={4}>
            <Label withInput={true}>{size.label}</Label>
            <Select triggerOptions={{ triggerSize: size.value }} onSelect={onSelectHandler}>
              <Select.List>
                {medicineList.map((item, key) => {
                  return (
                    <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                      {item.label}
                    </Select.Option>
                  );
                })}
              </Select.List>
            </Select>
          </Column>
        );
      })}
    </Row>
  );
}
```


#### Select

```jsx
import { Select } from '@innovaccer/design-system';

() => {
  const colourList = [
    { label: 'Red', value: 'Color_Red' },
    { label: 'Blue', value: 'Color_Blue' },
    { label: 'Green', value: 'Color_Green' },
    { label: 'Yellow', value: 'Color_Yellow' },
    { label: 'Orange', value: 'Color_Orange' },
    { label: 'Purple', value: 'Color_Purple' },
    { label: 'Pink', value: 'Color_Pink' },
    { label: 'Black', value: 'Color_Black' },
    { label: 'White', value: 'Color_White' },
    { label: 'Brown', value: 'Color_Brown' },
  ];

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };


  return (
    <Select triggerOptions={{ inlineLabel: 'colour', placeholder: 'Select' }} onSelect={onSelectHandler}>
      <Select.List>
        {colourList.map((item, key) => {
          return (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Select.Option>
          );
        })}
      </Select.List>
    </Select>
  );
}
```


#### Select

```jsx
import { Select } from '@innovaccer/design-system';

() => {
  const medicineList = [
    { label: 'Acetaminophen', value: 'Acetaminophen' },
    { label: 'Ibuprofen', value: 'Ibuprofen' },
    { label: 'Penicillin G', value: 'Penicillin G' },
    { label: 'Penbutolol', value: 'Penbutolol' },
    { label: 'Aminophenol', value: 'Aminophenol' },
    { label: 'Vancomycin', value: 'Vancomycin' },
    { label: 'Aspirin', value: 'Aspirin' },
    { label: 'Paracetamol', value: 'Paracetamol' },
    { label: 'Lisinopril', value: 'Lisinopril' },
    { label: 'Simvastatin', value: 'Simvastatin' },
    { label: 'Amoxicillin', value: 'Amoxicillin' },
    { label: 'Ciprofloxacin', value: 'Ciprofloxacin' },
    { label: 'Metformin', value: 'Metformin' },
  ];

  const [searchTerm, setSearchTerm] = React.useState('');
  const [filteredMedicines, setFilteredMedicines] = React.useState(medicineList);
  const [error, setError] = React.useState(false);

  React.useEffect(() => {
    if (searchTerm.trim() === '') {
      setFilteredMedicines(medicineList);
    }
    const newList = medicineList.filter((medicine) => medicine.label.toLowerCase().includes(searchTerm.toLowerCase()));

    setFilteredMedicines(newList);
    setError(newList.length === 0);
  }, [searchTerm]);

  const onChangeHandler = (value) => {
    setSearchTerm(value);
  };

  const onClearHandler = () => {
    setSearchTerm('');
  };

  const onSelectHandler = (selectedOption) => {
    console.log('selectedOption', selectedOption);
  };


  return (
    <Select onSelect={onSelectHandler}>
      <Select.SearchInput
        value={searchTerm}
        placeholder="Search"
        onChange={onChangeHandler}
        onClear={onClearHandler}
      ></Select.SearchInput>
      {error ? (
        <Select.EmptyTemplate
          description="Try modifying your search to find what you are looking for."
          size="small"
          title="No results found"
        ></Select.EmptyTemplate>
      ) : (
        <Select.List>
          {filteredMedicines.map((item, key) => (
            <Select.Option key={key} option={{ label: item.label, value: item.value }}>
              {item.label}
            </Select.Option>
          ))}
        </Select.List>
      )}
    </Select>
  );
}
```# SelectionCard



### Code Examples

#### SelectionCard

```jsx
import { Row, Column, SelectionCard, Icon, Text } from '@innovaccer/design-system';

() => {
  const { selectedCardIds, selectedCardValues, isCardSelected, updateCardSelection } = SelectionCard.useMultiSelect();

  const list = [
    {
      id: 'item1',
      iconName: 'key',
      title: 'Manual drop w/ SFTP user',
      description: 'Give access to data asset using SSH keys',
    },
    {
      id: 'item2',
      iconName: 'adjust',
      title: 'Manual drop on SFTP disk',
      description: 'Give access to a separate SFTP disk image',
    },
  ];

  React.useEffect(() => {
    console.log(selectedCardIds, selectedCardValues);
  }, [selectedCardIds]);

  const onClickHandler = (e, id, value) => {
    console.log('onClick handler', e, id, value);
    updateCardSelection(id, value);
  };

  return (
    <Row>
      {list.map((cardItem, key) => {
        const { id, iconName, title, description } = cardItem;
        return (
          <Column key={key} size={6}>
            <SelectionCard
              id={id}
              cardValue={cardItem}
              className="p-6 d-flex mr-6"
              onClick={onClickHandler}
              selected={isCardSelected(id)}
            >
              <Icon size={20} name={iconName} />
              <div className="ml-5">
                <Text weight="strong">{title}</Text>
                <br />
                <Text className="pt-2" appearance="subtle">{description}</Text>
              </div>
            </SelectionCard>
          </Column>
        );
      })}
    </Row>
  );
}
```


#### SelectionCard

```jsx
import { Text, SelectionCard, Icon } from '@innovaccer/design-system';

() => {
  return (
    <div>
      <Text weight="strong">Left Content Alignment:</Text>
      <SelectionCard name="item1" className="p-6 w-25 d-flex mb-8 mt-6" selected={true}>
        <Icon size={24} name="adjust" />
        <div className="ml-5">
          <Text weight="strong">Manual drop on SFTP disk</Text>
          <br />
          <Text className="pt-2" appearance="subtle">
            Give access to a separate SFTP disk image
          </Text>
        </div>
      </SelectionCard>

      <Text weight="strong">Center Content Alignment:</Text>
      <SelectionCard
        name="item2"
        className="p-6 w-25 mt-6 d-flex flex-column align-items-center text-align-center"
        selected={true}
      >
        <Icon size={24} name="adjust" className="mb-4" />
        <Text weight="strong" className="mb-2">
          Manual drop on SFTP disk
        </Text>
        <Text appearance="subtle">Give access to a separate SFTP disk image</Text>
      </SelectionCard>
    </div>
  );
}
```


#### SelectionCard

```jsx
import { Row, Column, SelectionCard, Icon, Text } from '@innovaccer/design-system';

() => {
  const { selectedCardIds, selectedCardValues, isCardSelected, updateCardSelection } = SelectionCard.useMultiSelect();

  const list = [
    {
      id: 'item1',
      iconName: 'transfer_within_a_station',
      title: 'ADT - Admit, Discharge, Transfer',
      description: 'ENS (Encounter notification system) data',
    },
    {
      id: 'item2',
      iconName: 'calendar_month',
      title: 'Appointments',
      description: 'PMS (Practice management system)',
    },
    {
      id: 'item3',
      iconName: 'receipt_long',
      title: 'Billing',
      description: 'Billing and charges',
    },
    {
      id: 'item4',
      iconName: 'account_balance',
      title: 'Claims',
      description: 'Medical, pharmacy, attribution',
    },
  ];

  React.useEffect(() => {
    console.log(selectedCardIds, selectedCardValues);
  }, [selectedCardIds]);

  const onClickHandler = (e, id, value) => {
    console.log('onClick handler', e, id, value);
    updateCardSelection(id, value);
  };

  return (
    <Row>
      {list.map((cardItem, key) => {
        const { id, iconName, title, description } = cardItem;
        return (
          <Column key={key} size={6} className="mb-6">
            <SelectionCard
              id={id}
              cardValue={cardItem}
              className="p-6 d-flex mr-6"
              onClick={onClickHandler}
              selected={isCardSelected(id)}
            >
              <Icon size={20} name={iconName} />
              <div className="ml-5">
                <Text weight="strong">{title}</Text>
                <br />
                <Text className="pt-2" appearance="subtle">{description}</Text>
              </div>
            </SelectionCard>
          </Column>
        );
      })}
    </Row>
  );
}
```


#### SelectionCard

```jsx
import { Row, Column, SelectionCard, Icon, Text } from '@innovaccer/design-system';

() => {
  const { selectedCardIds, selectedCardValues, isCardSelected, updateCardSelection } = SelectionCard.useSingleSelect();

  const list = [
    {
      id: 'item1',
      iconName: 'transfer_within_a_station',
      title: 'ADT - Admit, Discharge, Transfer',
      description: 'ENS (Encounter notification system) data',
    },
    {
      id: 'item2',
      iconName: 'calendar_month',
      title: 'Appointments',
      description: 'PMS (Practice management system)',
    },
    {
      id: 'item3',
      iconName: 'receipt_long',
      title: 'Billing',
      description: 'Billing and charges',
    },
    {
      id: 'item4',
      iconName: 'account_balance',
      title: 'Claims',
      description: 'Medical, pharmacy, attribution',
    },
  ];

  React.useEffect(() => {
    console.log(selectedCardIds, selectedCardValues);
  }, [selectedCardIds]);

  const onClickHandler = (e, id, value) => {
    console.log('onClick handler', e, id, value);
    updateCardSelection(id, value);
  };

  return (
    <Row>
      {list.map((cardItem, key) => {
        const { id, iconName, title, description } = cardItem;
        return (
          <Column key={key} size={6} className="mb-6">
            <SelectionCard
              id={id}
              cardValue={cardItem}
              className="p-6 d-flex mr-6"
              onClick={onClickHandler}
              selected={isCardSelected(id)}
            >
              <Icon size={20} name={iconName} />
              <div className="ml-5">
                <Text weight="strong">{title}</Text>
                <br />
                <Text className="pt-2" appearance="subtle">{description}</Text>
              </div>
            </SelectionCard>
          </Column>
        );
      })}
    </Row>
  );
}
```


#### SelectionCard

```jsx
import { Row, Column, Text, SelectionCard, Icon } from '@innovaccer/design-system';

() => {
  const cardConfigs = [
    { label: 'Default:', props: {} },
    { label: 'Disabled:', props: { disabled: true } },
    { label: 'Selected:', props: { selected: true } },
    { label: 'Selected and disabled:', props: { disabled: true, selected: true } },
  ];

  return (
    <Row>
      {cardConfigs.map((config, index) => (
        <Column key={index} size={6}>
          <Text weight="strong">{config.label}</Text>
          <SelectionCard className="p-6 d-flex mt-6 mb-8 mr-6" {...config.props}>
            <Icon size={20} name="adjust" />
            <div className="ml-5">
              <Text weight="strong">Manual drop on SFTP disk</Text>
              <br />
              <Text className="pt-2" appearance="subtle">
                Give access to a separate SFTP disk image
              </Text>
            </div>
          </SelectionCard>
        </Column>
      ))}
    </Row>
  );
}
```# Sidesheet

Side sheets are used to present a great amount of information as a part of users' primary task while maintaining the context with the background content.

### Code Examples

#### Sidesheet

```jsx
import { Button, Label, Text, Sidesheet } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(false);
  };

  const headerOptions = {
    heading: 'Heading',
    subHeading: 'Subheading',
  };

  const options = {
    onClose,
    open,
    headerOptions,
    footer: (
      <>
        <Button appearance="primary" className="mr-4">
          Primary
        </Button>
        <Button appearance="basic">Cancel</Button>
      </>
    ),
  };

  const SidesheetDescription = (params) => {
    const { label, description } = params;
    return (
      <div className="py-4">
        {label && <Label withInput={!!description}>{label}</Label>}
        {label && description && <br />}
        {description && <Text>{description}</Text>}
      </div>
    );
  };

  const sidesheetDescriptionOptions = {
    label: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
  };

  const optionsWithoutLabel = {
    description: 'Card Sections include supporting text like an article summary or a healthcare service description.',
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Sidesheet
      </Button>
      <Sidesheet {...options}>
        <SidesheetDescription {...sidesheetDescriptionOptions} />
        <SidesheetDescription {...optionsWithoutLabel} />
      </Sidesheet>
    </div>
  );
};
```


#### Sidesheet

```jsx
import { Button, Label, Text, Sidesheet, Heading, Badge, Divider } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const backdropClose = true;

  const onClose = () => {
    setOpen(false);
  };

  const options = {
    onClose,
    open,
    backdropClose,
    footer: (
      <>
        <Button appearance="primary" className="mr-4">
          Primary
        </Button>
        <Button appearance="basic">Cancel</Button>
      </>
    ),
  };

  const SidesheetDescription = (params) => {
    const { label, description } = params;
    return (
      <div className="py-4">
        {label && <Label withInput={!!description}>{label}</Label>}
        {label && description && <br />}
        {description && <Text>{description}</Text>}
      </div>
    );
  };

  const sidesheetDescriptionOptions = {
    label: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
  };

  const optionsWithoutLabel = {
    description: 'Card Sections include supporting text like an article summary or a healthcare service description.',
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Sidesheet
      </Button>
      <Sidesheet
        {...options}
        header={
          <div className="pl-7">
          <Heading size="m">Untitled document</Heading>
          <div className="d-flex mt-2">
            <div className="mr-3">
              <Badge>User Interface</Badge>
            </div>
            <div className="mr-3">
              <Badge>Design</Badge>
            </div>
            <div className="mr-3">
              <Badge>Development</Badge>
            </div>
          </div>
          <Divider />
        </div>
        }
      >
        <SidesheetDescription {...sidesheetDescriptionOptions} />
        <SidesheetDescription {...optionsWithoutLabel} />
      </Sidesheet>
    </div>
  );
};
```


#### Sidesheet

```jsx
import { Button, Sidesheet, Label, Input, InputMask, Radio, Textarea, Slider } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const dateMask = Utils.masks.date['mm/dd/yyyy'];
  const dateValidator = (val) => Utils.validators.date(val, 'mm/dd/yyyy');

  const onClose = () => {
    setOpen(!open);
  };

  const headerOptions = {
    heading: 'Goal details',
    subHeading: 'Comorbidities (e.g obesity, chronic rhinosinusitis, food allergy)',
  };

  const options = {
    onClose,
    open,
    headerOptions,
    seperator: true,
    footer: (
      <>
        <Button appearance="primary" className="mr-4">
          Add goal
        </Button>
        <Button appearance="basic">Cancel</Button>
      </>
    ),
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Sidesheet
      </Button>
      <Sidesheet {...options}>
        <div className="py-7">
          <div className="w-100">
            <Label required={true} withInput={true}>
              Goal
            </Label>
            <Input placeholder="Placeholder" />
          </div>
          <div className="d-flex mt-6">
            <div>
              <Label required={true} withInput={true}>
                Achieve by
              </Label>
              <InputMask icon="event" mask={dateMask} validators={dateValidator} placeholder="mm/dd/yyyy" />
            </div>
            <div className="ml-6">
              <Label required={true} withInput={true}>
                Priority
              </Label>
              <div className="d-flex py-3">
                <Radio className="mr-4" label="High" name="Priority" size="regular" value="High" />
                <Radio
                  defaultChecked={true}
                  className="mr-4"
                  label="Medium"
                  name="Priority"
                  size="regular"
                  value="Medium"
                />
                <Radio label="Low" name="Priority" size="regular" value="Low" />
              </div>
            </div>
          </div>
          <div className="mt-7">
            <Label withInput={true} required={true}>
              Care team interventions
            </Label>
            <Textarea
              className="mt-4"
              aria-labelledby="Textarea"
              name="Textarea"
              placeholder="Define intervention"
              resize={true}
              rows={5}
            />
            <Button className="mt-4" size="tiny" icon="refresh" iconAlign="left" appearance="transparent">
              Add intervention
            </Button>
          </div>
          <div className="mt-7">
            <Label className="d-block w-100" withInput={true}>
              Patient actions
            </Label>
            <Button className="mt-4" size="tiny" icon="refresh" iconAlign="left" appearance="transparent">
              Add patient action
            </Button>
          </div>
          <div className="pr-7 mt-7">
            <Label withInput={true}>Motivational score</Label>
            <Slider className="mt-6" defaultValue={2} label="Confidence" stepSize={1} />
            <Slider className="mt-8" defaultValue={2} label="Readiness" stepSize={1} />
            <Slider className="mt-8" defaultValue={2} label="Importance" stepSize={1} />
            <Slider className="mt-8" defaultValue={2} label="Punctuality" stepSize={1} />
            <Slider className="mt-8 mb-8" defaultValue={2} label="Clarity" stepSize={1} />
          </div>
        </div>
      </Sidesheet>
    </div>
  );
};
```


#### Sidesheet

```jsx
import { Button, Label, Text, Sidesheet, Paragraph } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(false);
  };

  const backIconCallback = () => {
    console.log('back icon clicked');
  };

  const headerOptions = {
    backIconCallback,
    backIcon: true,
    heading: 'Heading',
    subHeading: 'Subheading',
  };

  const options = {
    onClose,
    open,
    headerOptions,
    stickFooter: true,
    footer: (
      <>
        <Button appearance="primary" className="mr-4">
          Primary
        </Button>
        <Button appearance="basic">Cancel</Button>
      </>
    ),
  };

  const SidesheetDescription = (params) => {
    const { label, description } = params;
    return (
      <div className="py-4">
        {label && <Label withInput={!!description}>{label}</Label>}
        {label && description && <br />}
        {description && <Text>{description}</Text>}
      </div>
    );
  };

  const sidesheetDescriptionOptions = {
    label: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
  };

  const optionsWithoutLabel = {
    description: 'Card Sections include supporting text like an article summary or a healthcare service description.',
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Sidesheet
      </Button>
      <Sidesheet {...options}>
        <SidesheetDescription {...sidesheetDescriptionOptions} />
        <SidesheetDescription {...optionsWithoutLabel} />
        <Paragraph>
          The action buttons appear in the left side of the sheet and follows the reverse order as the modals to keep
          the position of primary action predictable. Also, if the content covers &gt;= 75% of the side sheet measured
          vertically, then the actions appear in the bottom, i.e, margin-bottom for the footer is 0px.
        </Paragraph>
      </Sidesheet>
    </div>
  );
};
```


#### Sidesheet

```jsx
import { Button, Label, Text, Sidesheet, Heading } from '@innovaccer/design-system';

() => {
  const [page, setPage] = React.useState(1);
  const [animate, setAnimate] = React.useState(true);
  const [open, setOpen] = React.useState(false);

  React.useEffect(() => {
    setAnimate(true);
    return () => {
      setAnimate(false);
    };
  }, [page]);

  const onClose = () => {
    setOpen(false);
    action('on close triggered')();
  };

  const backIconCallback = () => {
    action('back icon clicked')();
    setPage(1);
  };

  const headerOptions = {
    backIconCallback,
    backIcon: page === 2,
    heading: `Heading ${page}`,
    subHeading: 'Subheading',
  };

  const options = {
    onClose,
    open,
    headerOptions,
    stickFooter: true,
    backdropClose: true,
    footer: (
      <>
        {page === 1 && (
          <>
            <Button appearance="primary" className="mr-4" onClick={() => setPage(2)}>
              Next
            </Button>
            <Button appearance="basic">Cancel</Button>
          </>
        )}
        {page === 2 && (
          <>
            <Button appearance="primary" className="mr-4">
              Submit
            </Button>
            <Button appearance="basic" onClick={() => setPage(1)}>
              Back
            </Button>
          </>
        )}
      </>
    ),
  };

  const SidesheetDescription = (params) => {
    const { label, description } = params;
    return (
      <div className="py-4">
        {label && <Label withInput={!!description}>{label}</Label>}
        {label && description && <br />}
        {description && <Text>{description}</Text>}
      </div>
    );
  };

  const sidesheetDescriptionOptions = {
    label: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
  };

  const optionsWithoutLabel = {
    description: 'Card Sections include supporting text like an article summary or a healthcare service description.',
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Sidesheet
      </Button>
      <Sidesheet {...options}>
        <div className={animate ? 'fade-in' : ''} onAnimationEnd={() => setAnimate(false)}>
          <Heading size="s">{`Page ${page}`}</Heading>
          <SidesheetDescription {...sidesheetDescriptionOptions} />
          <SidesheetDescription {...optionsWithoutLabel} />
        </div>
      </Sidesheet>
    </div>
  );
};
```


#### Sidesheet

```jsx
import { Button, Label, Text, Sidesheet } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(false);
  };

  const headerOptions = {
    heading: 'Heading',
    subHeading: 'Subheading',
  };

  const options = {
    onClose,
    open,
    headerOptions,
    footer: (
      <>
        <Button appearance="primary" className="mr-4">
          Primary
        </Button>
        <Button appearance="basic">Basic</Button>
      </>
    ),
  };

  const SidesheetDescription = (params) => {
    const { label, description } = params;
    return (
      <div className="py-4">
        {label && <Label withInput={!!description}>{label}</Label>}
        {label && description && <br />}
        {description && <Text>{description}</Text>}
      </div>
    );
  };

  const sidesheetDescriptionOptions = {
    label: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
  };

  const optionsWithoutLabel = {
    description: 'Card Sections include supporting text like an article summary or a healthcare service description.',
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Sidesheet
      </Button>
      <Sidesheet {...options} dimension="large">
        <SidesheetDescription {...sidesheetDescriptionOptions} />
        <SidesheetDescription {...optionsWithoutLabel} />
      </Sidesheet>
    </div>
  );
};
```


#### Sidesheet

```jsx
import { Button, Label, Text, Sidesheet } from '@innovaccer/design-system';

() =>{
  const [open, setOpen] = React.useState(false);

  const onClose = () => {
    setOpen(false);
  };

  const headerOptions = {
    heading: 'Heading',
    subHeading: 'Subheading',
  };

  const options = {
    onClose,
    open,
    headerOptions,
    footer: (
      <>
        <Button appearance="primary" className="mr-4">
          Primary
        </Button>
        <Button appearance="basic">Basic</Button>
      </>
    ),
  };

  const SidesheetDescription = (params) => {
    const { label, description } = params;
    return (
      <div className="py-4">
        {label && <Label withInput={!!description}>{label}</Label>}
        {label && description && <br />}
        {description && <Text>{description}</Text>}
      </div>
    );
  };

  const sidesheetDescriptionOptions = {
    label: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
  };

  const optionsWithoutLabel = {
    description: 'Card Sections include supporting text like an article summary or a healthcare service description.',
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Sidesheet
      </Button>
      <Sidesheet {...options}>
        <SidesheetDescription {...sidesheetDescriptionOptions} />
        <SidesheetDescription {...optionsWithoutLabel} />
      </Sidesheet>
    </div>
  );
};
```


#### Sidesheet

```jsx
import { Button, Label, Text, Sidesheet, Modal, ModalDescription } from '@innovaccer/design-system';

() =>  {
  const [open, setOpen] = React.useState(false);
  const [openSecond, setOpenSecond] = React.useState(false);
  const backdropClose = true;

  const onClose = () => {
    setOpen(false);
  };

  const onCloseSecond = () => {
    setOpenSecond(false);
  };

  const headerOptions = {
    heading: 'Heading',
    subHeading: 'Subheading',
  };

  const options = {
    onClose,
    open,
    headerOptions,
    backdropClose,
    footer: (
      <>
        <Button appearance="primary" className="mr-4" onClick={() => setOpenSecond(true)}>
          Open
        </Button>
        <Button appearance="basic">Cancel</Button>
      </>
    ),
  };

  const SidesheetDescription = (params) => {
    const { label, description } = params;
    return (
      <div className="py-4">
        {label && <Label withInput={!!description}>{label}</Label>}
        {label && description && <br />}
        {description && <Text>{description}</Text>}
      </div>
    );
  };

  const sidesheetDescriptionOptions = {
    label: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
  };

  const optionsWithoutLabel = {
    description: 'Card Sections include supporting text like an article summary or a healthcare service description.',
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Sidesheet
      </Button>
      <Sidesheet {...options} closeOnEscape={true}>
        <SidesheetDescription {...sidesheetDescriptionOptions} />
        <SidesheetDescription {...optionsWithoutLabel} />
      </Sidesheet>

      <Modal
        closeOnEscape={true}
        open={openSecond}
        backdropClose={false}
        onClose={onCloseSecond}
        headerOptions={{
          heading: 'Heading Part Two',
          subHeading: 'Subheading Part Two',
        }}
        footer={
          <>
            <Button appearance="primary" className="ml-4">
              Primary
            </Button>
          </>
        }
      >
        <ModalDescription description="Card Sections include supporting text like an article summary or a healthcare service description." />
      </Modal>
    </div>
  );
};
```


#### Sidesheet

```jsx
import { Button, Label, Text, Sidesheet } from '@innovaccer/design-system';

() => {
  const [open, setOpen] = React.useState(false);
  const [openSecond, setOpenSecond] = React.useState(false);
  const backdropClose = true;

  const onClose = () => {
    setOpen(false);
  };

  const onCloseSecond = () => {
    setOpenSecond(false);
  };

  const headerOptions = {
    heading: 'Heading',
    subHeading: 'Subheading',
  };

  const options = {
    onClose,
    open,
    backdropClose,
    headerOptions,
    footer: (
      <>
        <Button appearance="primary" className="mr-4" onClick={() => setOpenSecond(true)}>
          Open
        </Button>
        <Button appearance="basic">Cancel</Button>
      </>
    ),
  };

  const SecondOverlayOptions = {
    headerOptions,
    backdropClose,
    onClose: onCloseSecond,
    open: openSecond,
    footer: (
      <>
        <Button appearance="primary" className="mr-4">
          Primary
        </Button>
      </>
    ),
  };

  const SidesheetDescription = (params) => {
    const { label, description } = params;
    return (
      <div className="py-4">
        {label && <Label withInput={!!description}>{label}</Label>}
        {label && description && <br />}
        {description && <Text>{description}</Text>}
      </div>
    );
  };

  const sidesheetDescriptionOptions = {
    label: 'Description Title',
    description: 'Adding a subheading clearly indicates the hierarchy of the information.',
  };

  const optionsWithoutLabel = {
    description: 'Card Sections include supporting text like an article summary or a healthcare service description.',
  };

  const sidesheetDescriptionOptions2 = {
    label: 'Description Title - 2',
    description: 'Adding a subheading clearly indicates the hierarchy of the information. - 2',
  };

  const optionsWithoutLabel2 = {
    description:
      'Card Sections include supporting text like an article summary or a healthcare service description. - 2',
  };

  return (
    <div>
      <Button appearance="primary" onClick={() => setOpen(true)}>
        Open Sidesheet
      </Button>
      <Sidesheet {...options} dimension="large" closeOnEscape={true}>
        <SidesheetDescription {...sidesheetDescriptionOptions} />
        <SidesheetDescription {...optionsWithoutLabel} />
      </Sidesheet>

      <Sidesheet {...SecondOverlayOptions} closeOnEscape={true}>
        <SidesheetDescription {...sidesheetDescriptionOptions2} />
        <SidesheetDescription {...optionsWithoutLabel2} />
      </Sidesheet>
    </div>
  );
};
```# Slider

A slider lets user select a value (or range) from a given range of values.

### Code Examples

#### Components Slider Slider All

```jsx
import { Slider } from '@innovaccer/design-system';

() => {
  const min = 0;
  const max = 10;
  const stepSize = 0.1;
  const labelStepSize = 1;
  const defaultValue = 4;
  const label = 'Slider Label';
  const disabled = false;

  const onChange = (value) => {
    return action(`new value: ${value}`);
  };

  const options = {
    min,
    max,
    stepSize,
    labelStepSize,
    label,
    disabled,
    defaultValue,
    onChange,
  };

  return <Slider key={defaultValue} className="my-8" {...options} />;
}
```


#### Components Slider Slider Custom Labels

```jsx
import { Slider } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(4);

  const onChange = (value) => {
    setValue(value);
  };

  const labelRenderer = (value) => {
    return `${value}%`;
  };

  return (
    <Slider
      min={1}
      max={10}
      stepSize={0.1}
      labelStepSize={1}
      value={value}
      onChange={onChange}
      labelRenderer={labelRenderer}
      className='my-8'
    />
  );
}
```


#### Components Slider Slider Disabled

```jsx
import { Slider } from '@innovaccer/design-system';

() => {
  return (
    <Slider
      className="my-8"
      label="Disabled Slider"
      disabled={true}
      stepSize={0.1}
      labelStepSize={1}
      defaultValue={4}
    />
  );
}
```


#### Components Slider Slider Types Controlled Slider

```jsx
import { Slider } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState(4);

  const onChange = (value) => {
    setValue(value);
  };

  return (
    <Slider
      min={1}
      max={10}
      label='Controlled Slider'
      stepSize={0.1}
      labelStepSize={1}
      value={value}
      onChange={onChange}
      className="my-8"
    />
  );
}
```


#### Components Slider Slider Types Uncontrolled Slider

```jsx
import { Slider } from '@innovaccer/design-system';

() => {
  return (
    <Slider
      min={1}
      max={10}
      label="Uncontrolled Slider"
      stepSize={0.1}
      labelStepSize={1}
      defaultValue={4}
      className="my-8"
    />
  );
}
```


#### Components Slider Slider Variants Discrete Slider

```jsx
import { Slider } from '@innovaccer/design-system';

() => {
  return (
    <Slider min={1} max={10} label="Discrete Slider" stepSize={1} labelStepSize={1} defaultValue={4} className="my-8" />
  );
}
```


#### Components Slider Slider Variants Free Slider

```jsx
import { Slider } from '@innovaccer/design-system';

() => {
  return (
    <Slider min={1} max={10} label="Free Slider" stepSize={0.1} labelStepSize={1} defaultValue={4} className="my-8" />
  );
}
```# Spinner



### Code Examples

#### Components Progress Indicators Spinner All

```jsx
import { Spinner } from '@innovaccer/design-system';

() => {
  return <Spinner />;
}
```


#### Spinner

```jsx
import { Spinner, Text } from '@innovaccer/design-system';

() => {
  const appearances = ['primary', 'secondary', 'white'];
  return (
    <div className="d-flex">
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="mr-8">
            <div className={appear === 'white' ? 'bg-dark' : 'bg-transparent'}>
              <Spinner appearance={appear} />
            </div>
            <Text weight="strong">{appear.charAt(0).toUpperCase() + appear.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### Components Progress Indicators Spinner Inline Loader

```jsx
import { Spinner, Text } from '@innovaccer/design-system';

() => (
  <div className="d-flex">
    <Spinner appearance="primary" size="small" className="mr-3" />
    <Text>uploading...</Text>
  </div>
)
```


#### Spinner

```jsx
import { Spinner, Text } from '@innovaccer/design-system';

() => {
  const sizes = ['xsmall', 'small', 'medium', 'large'];
  return (
    <div className="d-flex">
      {sizes.map((SpinnerSize, ind) => {
        return (
          <div key={ind} className="mr-8 d-flex flex-column align-items-center">
            <div className="h-75">
              <Spinner size={SpinnerSize} />
            </div>
            <Text weight="strong">{SpinnerSize.charAt(0).toUpperCase() + SpinnerSize.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```# StatusHint

Status hint is used to highlight the status of an item.

### Code Examples

#### Components StatusHint All

```jsx
import { StatusHint } from '@innovaccer/design-system';

() => {
  const children = 'Status Hint';

  const appearance = 'success';

  const options = {
    appearance,
  };

  return <StatusHint {...options}>{children}</StatusHint>;
}
```


#### Components StatusHint Label Wrap

```jsx
import { StatusHint } from '@innovaccer/design-system';

() => {
  const children = 'Status hint is used to highlight the status of an item.';

  const appearance = 'success';

  const options = {
    appearance,
  };

  return (
    <div className="d-flex">
      <StatusHint {...options} className="w-25" truncateLabel={true}>
        {children}
      </StatusHint>

      <StatusHint {...options} className="w-25 ml-10">
        {children}
      </StatusHint>
    </div>
  );
}
```


#### StatusHint

```jsx
import { StatusHint } from '@innovaccer/design-system';

() => <StatusHint appearance="alert">{'Alert'}</StatusHint>
```


#### StatusHint

```jsx
import { StatusHint } from '@innovaccer/design-system';

() => <StatusHint appearance="default">{'Default'}</StatusHint>
```


#### StatusHint

```jsx
import { StatusHint } from '@innovaccer/design-system';

() => <StatusHint appearance="info">{'Info'}</StatusHint>
```


#### StatusHint

```jsx
import { StatusHint } from '@innovaccer/design-system';

() => <StatusHint appearance="success">{'Success'}</StatusHint>
```


#### StatusHint

```jsx
import { StatusHint } from '@innovaccer/design-system';

() => <StatusHint appearance="warning">Warning</StatusHint>
```# Stepper



### Code Examples

#### Components Stepper All

```jsx
import { Stepper } from '@innovaccer/design-system';

() => {
  const [active, setActive] = React.useState(2);

  const steps = [
    {
      label: 'Step',
      value: 'Step1'
    },
    {
      label: 'Step',
      value: 'Step2'
    },
    {
      label: 'Step',
      value: 'Step3'
    },
    {
      label: 'Step',
      value: 'Step4'
    }
  ];

  const onChange = (index) => {
    setActive(index);
  };

  return (
    <Stepper
      steps={steps}
      active={active}
      completed={1}
      onChange={onChange}
    />
  );
}
```


#### Components Stepper Stepper In Page Header

```jsx
import { Stepper, Text, Avatar, Menu, Button, Breadcrumbs, Badge, MetaList, PageHeader } from '@innovaccer/design-system';

() => {
  const stepperData = [
    {
      value: 'step_1',
      label: 'Recipients',
    },
    {
      value: 'step_2',
      label: 'Message'
    },
    {
      value: 'step_3',
      label: 'Schedule',
    }
  ];

  const [active, setActive] = React.useState(2);

  const onChangeHandler = (activeStep) => {
    setActive(activeStep);
  };

  const stepper = <Stepper steps={stepperData} onChange={onChangeHandler} active={active} completed={1} />;

  const actions = (
    <div className="d-flex justify-content-end align-items-center">
      <Text className="mr-4" appearance="subtle" >Few minutes ago</Text>
      <Avatar className="mr-4" firstName="John" lastName="Doe" appearance="accent2"/>
      <div className="mr-4">
        <Menu trigger={<Menu.Trigger />}>
          <Menu.List>
            <Menu.Item>Option 1</Menu.Item>
            <Menu.Item>Option 2</Menu.Item>
            <Menu.Item>Option 3</Menu.Item>
          </Menu.List>
        </Menu>
      </div>
      <Button className="mr-4">Finish later</Button>
    </div>
  );

  const breadcrumbs = (
    <Breadcrumbs
      list={[{
        label: 'Campaigns',
        link: '/Campaigns'
      }]}
      onClick={link => console.log(`on-click: ${link}`)}
    />
  );

  const badge = (
    <Badge appearance="secondary">Message</Badge>
  );

  const meta = (
    <MetaList
      list={[{ label: 'Alert'}, { label: 'Draft' }]}
    />
  );

  return (
    <div className="p-6 bg-secondary-lightest" style={{width:'1200px'}}>
      <PageHeader
        title="Annual Wellness Visit"
        separator={true}
        navigationPosition="center"
        stepper={stepper}
        actions={actions}
        breadcrumbs={breadcrumbs}
        badge={badge}
        meta={meta}
      />
    </div>
  );
}
```


#### Components Stepper Stepper With Animation

```jsx
import { Card, Heading, Text, Row, Column, Label, Select, DateRangePicker, Icon, Checkbox, InputMask, Radio, Button, List, Stepper } from '@innovaccer/design-system';

() => {
  const steps = [
    {
      label: 'Step 1',
      value: 'Step1',
    },
    {
      label: 'Step 2',
      value: 'Step2',
    },
    {
      label: 'Step 3',
      value: 'Step3',
    },
  ];
  const [active, setActive] = React.useState(0);
  const [completed, setCompleted] = React.useState(-1);
  const [activeCard, setActiveCard] = React.useState(0);
  const [step, setStep] = React.useState(0);
  const maxSteps = steps.length;
  const [tab, setTab] = React.useState(1);
  const [skipIndices, setSkipIndices] = React.useState([]);

  const handleAnimationEnd = () => {
    if (step === activeCard) {
      setActiveCard(active);
    }
    setStep(active);
  };

  const getClasses = () => {
    if (activeCard !== active && step !== active) {
      if (tab === 1) {
        return 'slideOut-left';
      }
      else {
        return 'slideOut-right';
      }
    }
    else {
      if (tab === 1) {
        return 'slideIn-left';
      }
      else {
        return 'slideIn-right';
      }
    }
  }

  const step1 = () => {
    const options = [];
    for (let i = 1; i <= 10; i++) {
      options.push({
        label: `Option ${i}`,
        value: `Option ${i}`,
      });
    }
    return (
      <div
        className={`py-4 w-100 position-relative ${getClasses()}`}
        onAnimationEnd={handleAnimationEnd}
      >
        <Card className="px-6 py-6">
          <Heading className="mb-6" size="s">
            Configure Initiative
          </Heading>
          <Text weight="strong">Population Filter</Text>
          <Row className="mt-5 mb-4">
            <Column size={6} className="d-flex">
              <div className="mr-6 w-100">
                <Label withInput={true}>Region</Label>
                <Select triggerOptions={{ withClearButton: false }}>
                  <Select.List>
                    {options.map((item, key) => {
                      return (
                        <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                          {item.label}
                        </Select.Option>
                      );
                    })}
                  </Select.List>
                </Select>
              </div>
              <div className="w-100">
                <Label withInput={true}>Organization</Label>
                <Select triggerOptions={{ withClearButton: false }}>
                  <Select.List>
                    {options.map((item, key) => {
                      return (
                        <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                          {item.label}
                        </Select.Option>
                      );
                    })}
                  </Select.List>
                </Select>
              </div>
            </Column>
          </Row>
          <div className="pt-6">
            <Text weight="strong">Time Period</Text>
            <div className="mt-5">
              <DateRangePicker withInput />
            </div>
          </div>
        </Card>
      </div>
    );
  };

  const step2 = () => {
    const languages = [
      {
        label: 'Hindi',
        value: 'Hindi',
      },
      {
        label: 'English',
        value: 'English',
        selected: true,
      },
      {
        label: 'French',
        value: 'French',
      },
    ];
    const method = [
      {
        label: 'Phone',
        value: 'Phone',
      },
      {
        label: 'Message',
        value: 'Message',
        selected: true,
      },
      {
        label: 'Email',
        value: 'Email',
      },
      {
        label: 'Letter',
        value: 'Letter',
      },
    ];

    return (
      <div
        className={`py-4 w-100 position-relative ${getClasses()}`}
        onAnimationEnd={handleAnimationEnd}
      >
        <Card className="px-6 py-6">
          <form>
            <Row className="mb-6">
              <Column size={3} className="d-flex align-items-center">
                <Icon className="mr-4" name="language" />
                <Text>Known Languages</Text>
              </Column>
              <Column size={8} className="d-flex align-items-center">
                <div className="mr-5 w-25 align-items-center">
                  <Select
                    width
                    value={{ label: 'English', value: 'English' }}
                    triggerOptions={{ withClearButton: false }}
                  >
                    <Select.List>
                      {languages.map((item, key) => {
                        return (
                          <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                            {item.label}
                          </Select.Option>
                        );
                      })}
                    </Select.List>
                  </Select>
                </div>
                <Checkbox className="align-items-center" name="defaultLanguage" label="Set as Default" />
              </Column>
            </Row>
            <Row className="my-5">
              <Column className="d-flex align-items-center" size={3}>
                <Icon className="mr-4" name="record_voice_over" />
                <Text>Preferred Method of Contact</Text>
              </Column>
              <Column size={8} className="d-flex align-items-center">
                <Select value={{ label: 'Message', value: 'Message' }} triggerOptions={{ withClearButton: false }}>
                  <Select.List>
                    {method.map((item, key) => {
                      return (
                        <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                          {item.label}
                        </Select.Option>
                      );
                    })}
                  </Select.List>
                </Select>
              </Column>
            </Row>
            <Row className="mt-6">
              <Column size={3} className="d-flex align-items-center">
                <Icon className="mr-4" name="call" />
                <Text>Phone Numbers</Text>
              </Column>
              <Column size={8} className="d-flex align-items-center">
                <InputMask
                  mask={['(', /[1-9]/, /\d/, /\d/, ')', ' ', /\d/, /\d/, /\d/, '-', /\d/, /\d/, /\d/, /\d/]}
                  placeholder="(___) ___-____"
                  className="mr-4"
                  name="primaryPhoneNumber"
                />
                <Radio name="defaultPhoneNumber" value="defaultPrimaryPhoneNumber" label="Mark as Preferred" />
              </Column>
            </Row>
            <Row className="my-5">
              <Column size={3} className="d-flex align-items-center" />
              <Column size={8} className="d-flex">
                <InputMask
                  mask={['(', /[1-9]/, /\d/, /\d/, ')', ' ', /\d/, /\d/, /\d/, '-', /\d/, /\d/, /\d/, /\d/]}
                  placeholder="(___) ___-____"
                  className="mr-4"
                  name="secondaryPhoneNumber"
                />
                <Radio name="defaultPhoneNumber" value="defaultSecondaryPhoneNumber" label="Mark as Preferred" />
              </Column>
            </Row>
          </form>
        </Card>
      </div>
    );
  };

  const step3 = () => {
    const data = [
      {
        firstName: 'John',
        lastName: 'Doe',
        email: 'jonathandoe@gamil.com',
        owner: true,
      },
      {
        firstName: 'Katty',
        lastName: 'Perry',
        email: 'kattyperry21@gamil.com',
        edit: true,
      },
      {
        firstName: 'Daniel',
        lastName: 'Low',
        email: 'daniellow02@yahoo.com',
        view: true,
      },
    ];

    const schema = [
      {
        name: 'info',
        displayName: 'Info',
        width: '80%',
        cellType: 'AVATAR_WITH_META_LIST',
        translate: (a) => ({
          firstName: a.firstName,
          lastName: a.lastName,
          title: `${a.firstName} ${a.lastName}`,
          metaList: [a.email],
        }),
      },
      {
        name: 'rights',
        displayName: 'Rights',
        width: '20%',
        cellRenderer: (props) => {
          const renderRights = () => {
            if (props.data.owner) {
              return (
                <Text appearance="subtle" className="pr-5">
                  owner
                </Text>
              );
            }

            if (props.data.edit || props.data.view) {
              const rights = props.data.edit ? 'edit' : 'view';
              return (
                <Button
                  icon="keyboard_arrow_down"
                  iconAlign="right"
                  appearance="transparent"
                  onClick={(e) => e.stopPropagation()}
                >
                  {`can ${rights}`}
                </Button>
              );
            }

            return null;
          };

          return <div className="d-flex align-items-center justify-content-end flex-grow-1">{renderRights()}</div>;
        },
      },
    ];

    return (
      <div
        className={`py-4 w-100 position-relative ${getClasses()}`}
        onAnimationEnd={handleAnimationEnd}
      >
        <Card className="pt-4">
          <Text size="large" weight="strong" className="ml-5">
            Sharing Test Manual
          </Text>
          <List
            type="resource"
            withHeader={true}
            headerOptions={{
              withSearch: true,
              dynamicColumn: false,
            }}
            separator={false}
            showMenu={false}
            data={data}
            schema={schema}
            withPagination={false}
            onSearch={(currData, searchTerm) => {
              return currData.filter(
                (d) =>
                  d.firstName.toLowerCase().match(searchTerm.toLowerCase()) ||
                  d.lastName.toLowerCase().match(searchTerm.toLowerCase())
              );
            }}
          />
        </Card>
      </div>
    );
  };

  const onChange = (activeStep) => {
    if (activeStep < active) {
      setTab(0);
    } else {
      setTab(1);
    }
    setActive(activeStep);
  };

  const onNextHandler = () => {
    setTab(1);
    if (skipIndices.includes(active)) {
      const updatedSkip = [...skipIndices];
      const index = skipIndices.findIndex((skippedIndex) => skippedIndex === active);
      updatedSkip.splice(index, 1);
      setSkipIndices([...updatedSkip]);
    }
    setCompleted(active);
    setActive(active + 1);
  };

  const onSkipHandler = () => {
    setTab(1);
    if (!skipIndices.includes(active)) {
      setSkipIndices([...skipIndices, active]);
    }
    setActive(active + 1);
  };

  const onPreviousHandler = () => {
    setTab(0);
    if (skipIndices.includes(active)) {
      const updatedSkip = [...skipIndices];
      const index = skipIndices.findIndex((skippedIndex) => skippedIndex === active);
      updatedSkip.splice(index, 1);
      setSkipIndices([...updatedSkip]);
    }
    setCompleted(active - 1);
    setActive(active - 1);
  };

  const resetStepper = () => {
    setTab(1);
    setActive(0);
    setActiveCard(0);
    setCompleted(-1);
    setStep(0);
    setSkipIndices([]);
  };

  const renderStep = () => {
    switch (step) {
      case 0:
        return step1();
      case 1:
        return step2();
      case 2:
        return step3();
    }
  };

  return (
    <div className="d-flex flex-column py-4 px-6 bg-secondary-lightest">
      <div className="d-flex justify-content-center py-5 w-100">
        <Stepper steps={steps} active={active} completed={completed} onChange={onChange} skipIndexes={skipIndices} />
      </div>
      {renderStep()}
      <div className="w-100 d-flex justify-content-between">
        {active === maxSteps ? (
          <div className="w-100 d-flex justify-content-center">
            <Button onClick={resetStepper}>Reset</Button>
          </div>
        ) : (
          <div className="my-4 w-100 d-flex justify-content-between">
            <Button onClick={onPreviousHandler} disabled={active === 0}>
              Previous
            </Button>
            <div className="d-flex flex-row">
              <Button className="mr-4" onClick={onSkipHandler}>
                {active < maxSteps - 1 ? 'Skip' : 'Skip and Finish'}
              </Button>
              <Button onClick={onNextHandler} appearance="primary">
                {active < maxSteps - 1 ? 'Next' : 'Finish'}
              </Button>
            </div>
          </div>
        )}
      </div>
    </div>
  );
}
```


#### Components Stepper Variants Active Step

```jsx
import { Stepper } from '@innovaccer/design-system';

() => {
  const [active, setActive] = React.useState(0);

  const steps = [
    {
      label: 'Step',
      value: 'Step1'
    },
    {
      label: 'Step',
      value: 'Step2'
    },
    {
      label: 'Step',
      value: 'Step3'
    },
    {
      label: 'Step',
      value: 'Step4'
    }
  ];

  const onChange = (index) => {
    setActive(index);
  };

  return (
    <Stepper
      steps={steps}
      active={active}
      onChange={onChange}
    />
  );
}
```


#### Components Stepper Variants Completed Step

```jsx
import { Stepper } from '@innovaccer/design-system';

() => {
  const [active, setActive] = React.useState(3);

  const steps = [
    {
      label: 'Step',
      value: 'Step1'
    },
    {
      label: 'Step',
      value: 'Step2'
    },
    {
      label: 'Step',
      value: 'Step3'
    },
    {
      label: 'Step',
      value: 'Step4'
    }
  ];

  const onChange = (index) => {
    setActive(index);
  };

  return (
    <Stepper
      steps={steps}
      active={active}
      completed={2}
      onChange={onChange}
    />
  );
}
```


#### Components Stepper Variants Stepper With Skip

```jsx
import { Stepper, Button } from '@innovaccer/design-system';

() => {
  const steps = [
    {
      label: 'Step 1',
      value: 'Step1',
    },
    {
      label: 'Step 2',
      value: 'Step2',
    },
    {
      label: 'Step 3',
      value: 'Step3',
    },
  ];
  const [active, setActive] = React.useState(0);
  const [completed, setCompleted] = React.useState(-1);
  const maxSteps = steps.length;
  const [skipIndices, setSkipIndices] = React.useState([]);

  const onChange = (activeStep) => {
    return action(`Active Index: ${activeStep}`)();
  };

  const onNextHandler = () => {
    if (skipIndices.includes(active)) {
      const updatedSkip = [...skipIndices];
      const index = skipIndices.findIndex((skippedIndex) => skippedIndex === active);
      updatedSkip.splice(index, 1);
      setSkipIndices([...updatedSkip]);
    }
    setCompleted(active);
    setActive(active + 1);
  };

  const onSkipHandler = () => {
    if (!skipIndices.includes(active)) {
      setSkipIndices([...skipIndices, active]);
    }
    setActive(active + 1);
  };

  const onPreviousHandler = () => {
    if (skipIndices.includes(active)) {
      const updatedSkip = [...skipIndices];
      const index = skipIndices.findIndex((skippedIndex) => skippedIndex === active);
      updatedSkip.splice(index, 1);
      setSkipIndices([...updatedSkip]);
    }
    setCompleted(active - 1);
    setActive(active - 1);
  };

  const resetStepper = () => {
    setActive(0);
    setCompleted(-1);
    setSkipIndices([]);
  };

  return (
    <div className="d-flex flex-column py-4 px-6 bg-secondary-lightest">
      <div className="d-flex justify-content-center py-5 w-100">
        <Stepper steps={steps} active={active} completed={completed} onChange={onChange} skipIndexes={skipIndices} />
      </div>
      <div className="w-100 d-flex mt-12 justify-content-between">
        {active === maxSteps ? (
          <div className="w-100 d-flex justify-content-center">
            <Button onClick={resetStepper}>Reset</Button>
          </div>
        ) : (
          <div className="my-4 w-100 d-flex justify-content-between">
            <Button onClick={onPreviousHandler} disabled={active === 0}>
              Previous
            </Button>
            <div className="d-flex flex-row">
              <Button className="mr-4" onClick={onSkipHandler}>
                {active < maxSteps - 1 ? 'Skip' : 'Skip and Finish'}
              </Button>
              <Button onClick={onNextHandler} appearance="primary">
                {active < maxSteps - 1 ? 'Next' : 'Finish'}
              </Button>
            </div>
          </div>
        )}
      </div>
    </div>
  )
}
```# Subheading



### Code Examples

#### Subheading

```jsx
import { Subheading } from '@innovaccer/design-system';

() => {
  return <Subheading>Subheading component have different variants, look for options in knobs tab.</Subheading>;
}
```


#### Subheading

```jsx
import { Subheading, Text } from '@innovaccer/design-system';

() => {
  const appearances = ['default', 'subtle', 'disabled', 'white'];

  return (
    <div className="d-flex">
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="mr-6">
            <div className={appear === 'white' ? 'bg-dark' : 'bg-transparent'}>
              <Subheading appearance={appear}>Subheading</Subheading>
            </div>
            <br />
            <Text weight="strong">{appear.charAt(0).toUpperCase() + appear.slice(1)}</Text>
          </div>
        );
      })}
    </div>
  );
}
```


#### Subheading

```jsx
import { Subheading } from '@innovaccer/design-system';

() => {
  const colorList = [
    [
      'primary',
      'primary-dark',
      'primary-darker',
      'primary-light',
      'primary-lighter',
      'primary-lightest',
      'primary-shadow',
    ],
    [
      'success',
      'success-dark',
      'success-darker',
      'success-light',
      'success-lighter',
      'success-lightest',
      'success-shadow',
    ],
    ['alert', 'alert-dark', 'alert-darker', 'alert-light', 'alert-lighter', 'alert-lightest', 'alert-shadow'],
    [
      'warning',
      'warning-dark',
      'warning-darker',
      'warning-light',
      'warning-lighter',
      'warning-lightest',
      'warning-shadow',
    ],
    [
      'accent1',
      'accent1-dark',
      'accent1-darker',
      'accent1-light',
      'accent1-lighter',
      'accent1-lightest',
      'accent1-shadow',
    ],
    [
      'accent2',
      'accent2-dark',
      'accent2-darker',
      'accent2-light',
      'accent2-lighter',
      'accent2-lightest',
      'accent2-shadow',
    ],
    [
      'accent3',
      'accent3-dark',
      'accent3-darker',
      'accent3-light',
      'accent3-lighter',
      'accent3-lightest',
      'accent3-shadow',
    ],
    [
      'accent4',
      'accent4-dark',
      'accent4-darker',
      'accent4-light',
      'accent4-lighter',
      'accent4-lightest',
      'accent4-shadow',
    ],
    ['secondary', 'secondary-dark', 'secondary-light', 'secondary-lighter', 'secondary-lightest', 'secondary-shadow'],

    ['white', 'inverse', 'inverse-light', 'inverse-lighter', 'inverse-lightest', 'inverse-shadow'],
  ];

  return (
    <div>
      {colorList.map((colors, key) => {
        return (
          <div key={key} className="d-flex justify-content-between w-100 py-4">
            {colors.map((color, ind) => {
              return (
                <Subheading key={ind} color={color} className={color === 'white' ? 'bg-dark' : ''}>
                  {color}
                </Subheading>
              );
            })}
          </div>
        );
      })}
    </div>
  );
}
```# Switch

Switches are used to toggle between two states in a user interface - ON and OFF, hence resembling the real-life switches used to turn something ON or OFF.

### Code Examples

#### Switch

```jsx
import { Switch } from '@innovaccer/design-system';

() => <Switch aria-label="Default Checked Switch" defaultChecked={true} size="regular" />
```


#### Switch

```jsx
import { Switch, Text } from '@innovaccer/design-system';

() => {
  const sizes = ['tiny', 'regular'];

  return (
    <>
      <div className="d-flex mb-7">
        {sizes.map((switchSize, ind) => {
          return (
            <Switch
              key={ind}
              aria-label={`Switch ${switchSize}`}
              defaultChecked={true}
              size={switchSize}
              className="mr-9"
            />
          );
        })}
      </div>
      <div className="d-flex">
        {sizes.map((switchSize, ind) => {
          return (
            <Text key={ind} weight="strong" className="mr-9">
              {switchSize.charAt(0).toUpperCase() + switchSize.slice(1)}
            </Text>
          );
        })}
      </div>
    </>
  );
}
```


#### Switch

```jsx
import { Switch, Text } from '@innovaccer/design-system';

() => {
  return (
    <>
      <div className="d-flex mb-7 justify-content-between w-75">
        <Switch aria-label="Switch enabled" defaultChecked={true} />
        <Switch aria-label="Switch disabled" defaultChecked={true} disabled={true} />
        <Switch aria-label="Switch disabled" disabled={true} />
      </div>
      <div className="d-flex justify-content-between w-75">
        <Text weight="strong">Enabled</Text>
        <Text weight="strong">Enabled - Disabled</Text>
        <Text weight="strong">Disabled</Text>
      </div>
    </>
  );
}
```


#### Components Switch With Label

```jsx
import { Label, Switch } from '@innovaccer/design-system';

() => {
  const [checked, setChecked] = React.useState(false);

  const onChangeHandler = (_event, checkedValue) => {
    setChecked(!checked);
    return action(`switch-change: ${checkedValue}`)();
  };

  return (
    <form>
      <Label htmlFor="vaccination-status" withInput={true}>
        Have you been vaccinated ?
      </Label>
      <br />
      <Switch id="vaccination-status" checked={checked} onChange={onChangeHandler} />
    </form>
  );
}
```# Table

Tables are used for arranging information in a tabular format by laying out resource items, displaying data heavily based on numbers, or a list of homogenous items in their simplest form.

### Code Examples

#### Components Table All

```jsx
import { Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      firstName: 'Brooke',
      lastName: 'Heeran',
      email: 'bheeran0@altervista.org',
      gender: 'Female',
      status: 'Failed',
    },
    {
      firstName: 'Frazer',
      lastName: 'Cathro',
      email: 'fcathro1@ucla.edu',
      gender: 'Male',
      status: 'Failed',
    },
    {
      firstName: 'Lemmie',
      lastName: 'Ciric',
      email: {
        title: 'lciric2@dmoz.org',
        metaList: ['First', 'Second'],
      },
      gender: 'Male',
      status: 'Completed',
    },
    {
      firstName: 'Randy',
      lastName: 'Boatwright',
      email: 'rboatwright3@arstechnica.com',
      status: 'Completed',
      gender: 'Male',
    },
    {
      firstName: 'Rolando',
      lastName: 'Cyples',
      email: 'rcyples4@biglobe.ne.jp',
      gender: 'Male',
      status: 'Failed',
    },
    {
      firstName: 'Lem',
      lastName: 'Males',
      email: 'lmales5@admin.ch',
      gender: 'Male',
      status: 'Failed',
    },
    {
      firstName: 'Sayres',
      lastName: 'Adelberg',
      email: 'sadelberg6@uol.com.br',
      gender: 'Male',
      status: 'Completed',
    },
    {
      firstName: 'Murray',
      lastName: 'Bravington',
      email: 'mbravington7@drupal.org',
      gender: 'Male',
      status: 'Failed',
    },
    {
      firstName: 'Jena',
      lastName: 'Swatheridge',
      email: 'jswatheridge8@npr.org',
      gender: 'Female',
      status: 'Failed',
    },
    {
      firstName: 'Annabel',
      lastName: 'Nelsey',
      email: 'anelsey9@google.com',
      gender: 'Female',
      status: 'Completed',
    },
  ];

  const schema = [
    {
      name: 'firstName',
      displayName: 'Name',
      cellType: 'AVATAR_WITH_TEXT',
      width: '25%',
      translate: (a) => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName,
      }),
    },
    {
      name: 'email',
      displayName: 'Email',
      width: '25%',
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: '25%',
    },
    {
      name: 'status',
      displayName: 'Status',
      width: '25%',
    },
  ];

  return (
    <div className="vh-50">
      <Card className="h-100 overflow-hidden">
        <Table
          page={1}
          data={data}
          schema={schema}
          showMenu={true}
          withHeader={true}
          withPagination={true}
          pageSize={4}
          headerOptions={{
            withSearch: true,
          }}
        />
      </Card>
    </div>
  );
}
```


#### Components Table Alignment

```jsx
import { Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      id: '89092830',
      priority: 'Urgent',
      providerDetails: {
        title: 'Dr. John Doe',
        metaList: ['Bancroft Medical Clinic'],
      },
      sourceDetails: {
        title: 'Medical',
        metaList: ['InNote'],
      },
      patientDetails: {
        title: 'Brooklyn Simmons',
        metaList: ['Male', '12/12/2020'],
      },
    },
    {
      id: '89092834',
      priority: 'Urgent',
      providerDetails: {
        title: 'Jenny Wilson',
        metaList: ['Bancroft Medical Clinic'],
      },
      sourceDetails: {
        title: 'Medical',
        metaList: ['InNote'],
      },
      patientDetails: {
        title: 'Theresa Webb',
        metaList: ['Male', '12/12/2020'],
      },
    },
    {
      id: '89092124',
      priority: 'Urgent',
      providerDetails: {
        title: 'Devon Lane',
        metaList: ['Bancroft Medical Clinic'],
      },
      sourceDetails: {
        title: 'Behavioral health',
        metaList: ['InNote'],
      },
      patientDetails: {
        title: 'Dianne Russell',
        metaList: ['Male', '01/08/2020'],
      },
    },
    {
      id: '87329072',
      priority: 'Urgent',
      providerDetails: {
        title: 'Jerome Bell',
        metaList: ['Bancroft Medical Clinic'],
      },
      sourceDetails: {
        title: 'Medical',
        metaList: ['Phone/Email'],
      },
      patientDetails: {
        title: 'Floyd Miles',
        metaList: ['Male', '09/08/2020'],
      },
    },
    {
      id: '89092855',
      priority: 'Urgent',
      providerDetails: {
        title: 'Jenny Wilson',
        metaList: ['Bancroft Medical Clinic'],
      },
      sourceDetails: {
        title: 'Medical',
        metaList: ['Phone/Email'],
      },
      patientDetails: {
        title: 'Albert Flores',
        metaList: ['Male', '06/12/1997'],
      },
    },
  ];

  const schema = [
    {
      name: 'patientDetails',
      displayName: 'Name',
      cellType: 'WITH_META_LIST',
      width: '20%',
      verticalAlign: 'top',
    },
    {
      name: 'id',
      displayName: 'ID',
      width: '20%',
      verticalAlign: 'top',
    },
    {
      name: 'providerDetails',
      displayName: 'Provider',
      cellType: 'WITH_META_LIST',
      width: '20%',
      verticalAlign: 'top',
    },
    {
      name: 'sourceDetails',
      displayName: 'Type & source',
      cellType: 'WITH_META_LIST',
      width: '20%',
      verticalAlign: 'top',
    },
    {
      name: 'priority',
      displayName: 'Priority',
      width: '20%',
      verticalAlign: 'top',
    },
  ];

  return (
    <div className="vh-50">
      <Card className="h-100 overflow-hidden">
        <Table
          page={1}
          data={data}
          schema={schema}
          showMenu={true}
          withHeader={true}
          withPagination={true}
          withCheckbox={true}
          pageSize={5}
          checkboxAlignment="top"
          headerOptions={{
            withSearch: true,
          }}
        />
      </Card>
    </div>
  );
}
```


#### Async Table

```jsx
import { Icon, GridCell, Button, Card, Table } from '@innovaccer/design-system';


() => {
  const translateData = (schema, data) => {
    let newData = data;

    if (schema.translate) {
      const translatedData = schema.translate(data);
      newData = {
        ...newData,
        [schema.name]: typeof translatedData === 'object' ? {
          ...newData[schema.name],
          ...translatedData
        } : translatedData
      };
    }
    if (typeof newData[schema.name] !== 'object') newData[schema.name] = { title: newData[schema.name] };

    return newData;
  }

  const filterData = (schema, data, filterList) => {
    let filteredData = data;
    if (filterList) {
      Object.keys(filterList).forEach(schemaName => {
        const filters = filterList[schemaName];
        const sIndex = schema.findIndex(s => s.name === schemaName);
        const { onFilterChange } = schema[sIndex];
        if (filters.length && onFilterChange) {
          filteredData = filteredData.filter(d => onFilterChange(d, filters));
        }
      });
    }

    return filteredData;
  };

  const sortData = (schema, data, sortingList) => {
    const sortedData = [...data];
    sortingList.forEach(l => {
      const sIndex = schema.findIndex(s => s.name === l.name);
      if (sIndex !== -1) {
        const defaultComparator = (a, b) => {
          const aData = translateData(schema[sIndex], a);
          const bData = translateData(schema[sIndex], b);
          return aData[l.name].title.localeCompare(bData[l.name].title);
        };

        const {
          comparator = defaultComparator
        } = schema[sIndex];

        sortedData.sort(comparator);
        if (l.type === 'desc') sortedData.reverse();
      }
    });

    return sortedData;
  };

  const paginateData = (data, page, pageSize) => {
    const start = (page - 1) * pageSize;
    const end = start + pageSize;
    const paginatedData = data.slice(start, end);
    return paginatedData;
  };

  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];
  const [formattedData, setFormattedData] = React.useState(data);

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: 300,
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
      cellType: 'WITH_META_LIST'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      cellType: 'WITH_META_LIST',
      sorting: false,
      cellRenderer: props => {
        return (
          <>
            <Icon className="mr-5" name="events" />
            <GridCell
              {...props}
              schema={{
                ...props.schema,
                name: 'email'
              }}
            />
          </>
        );
      }
    },
  ];

  const fetchData = (options) => {
    const {
      page,
      pageSize,
      sortingList,
      filterList,
      searchTerm
    } = options;

    const onSearch = (d, searchTerm = '') => {
      return (
        d.firstName.toLowerCase().match(searchTerm.toLowerCase())
        || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
      );

      return true;
    }

    const filteredData = filterData(schema, data, filterList);
    const searchedData = filteredData.filter(d => onSearch(d, searchTerm));
    const sortedData = sortData(schema, searchedData, sortingList);
    setFormattedData(sortedData);

    if (page && pageSize) {
      return new Promise(resolve => {
        window.setTimeout(() => {
          const start = (page - 1) * pageSize;
          const end = start + pageSize;
          const slicedData = sortedData.slice(start, end);
          resolve({
            searchTerm,
            schema,
            count: sortedData.length,
            data: slicedData,
          });
        }, 2000);
      });
    }

    return new Promise(resolve => {
      window.setTimeout(() => {
        resolve({
          searchTerm,
          schema,
          count: sortedData.length,
          data: sortedData,
        });
      }, 2000);
    });
  }

  const loaderSchema = [
    {
        "name": "name",
        "displayName": "Name",
        "width": "40%",
        "resizable": true,
        "tooltip": true,
        "separator": true,
        "filters": [
            {
                "label": "A-G",
                "value": "a-g"
            },
            {
                "label": "H-R",
                "value": "h-r"
            },
            {
                "label": "S-Z",
                "value": "s-z"
            }
        ],
        "cellType": "AVATAR_WITH_TEXT"
    },
    {
        "name": "email",
        "displayName": "Email",
        "width": 250,
        "resizable": true,
        "sorting": false,
        "cellType": "WITH_META_LIST"
    },
    {
        "name": "gender",
        "displayName": "Gender",
        "width": 180,
        "resizable": true,
        "cellType": "STATUS_HINT",
        "filters": [
            {
                "label": "Male",
                "value": "male"
            },
            {
                "label": "Female",
                "value": "female"
            }
        ]
    },
    {
        "name": "icon",
        "displayName": "Icon",
        "width": 100,
        "resizable": true,
        "align": "center",
        "cellType": "ICON"
    },
    {
        "name": "customCell",
        "displayName": "Custom Cell",
        "width": 200,
        "resizable": true,
        "cellType": "WITH_META_LIST"
    }
];

  const onDataExport = (data) => {
    console.log("Exporting data", data);
  }

  const globalActionTrigger = (data) => {
    return (<Button onClick={() => onDataExport(data)}>Export</Button>);
  } 

  const selectionActionRenderer = (selectedData, selectAll) => {
    console.log('selectedData in output', selectedData, 'selectAll', selectAll);
    return (
      <div className="d-flex align-items-center">
        <Button size="tiny" className="mr-4">Delete</Button>
        <Button size="tiny">Export</Button>
      </div>
    )
  }

  return (
    <div>
      <Card className="h-100 overflow-hidden">
        <Table
          loaderSchema={loaderSchema}
          fetchData={fetchData}
          withHeader={true}
          uniqueColumnName="firstName"
          headerOptions={{
            selectionActionRenderer,
            withSearch: true,
            globalActionRenderer : globalActionTrigger,
            allowSelectAll: true,
          }}
          withCheckbox={true}
          onSelect={(rowIndex, selected, selectedList, selectAll) => console.log(`on-select: - rowIndex: ${ rowIndex } selected: ${ selected } selectedList: ${ JSON.stringify(selectedList) } selectAll: ${ selectAll } `)}
          withPagination={true}
          pageSize={5}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
    </div>
  );
};

```


#### Custom Body Cell Renderer

```jsx
import { PlaceholderParagraph, EditableInput, Card, Table } from '@innovaccer/design-system';


() => {
  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];

  const schema = [
  {
    name: 'name',
    displayName: 'Name',
    width: '40%',
    resizable: true,
    tooltip: true,
    separator: true,
    translate: (a) => ({
      title: `${a.firstName} ${a.lastName}`,
      firstName: a.firstName,
      lastName: a.lastName,
    }),
    filters: [
      { label: 'A-G', value: 'a-g' },
      { label: 'H-R', value: 'h-r' },
      { label: 'S-Z', value: 's-z' },
    ],
    onFilterChange: (a, filters) => {
      for (const filter of filters) {
        switch (filter) {
          case 'a-g':
            if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
            break;
          case 'h-r':
            if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
            break;
          case 's-z':
            if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
            break;
        }
      }
      return false;
    },
    cellType: 'AVATAR_WITH_TEXT',
  },
  {
    name: 'customCell',
    displayName: 'Custom Cell',
    width: 200,
    resizable: true,
    cellRenderer: (props) => {
      const { loading } = props;

      if (loading) return <PlaceholderParagraph length="medium" />;

      const [weight, setWeight] = React.useState('');

      const onChangeWeight = (value) => {
        setWeight(value);
      };

      return <EditableInput placeholder="Add Weight" value={weight} onChange={onChangeWeight} size="tiny" />;
    },
  },
  {
    name: 'email',
    displayName: 'Email',
    width: 250,
    resizable: true,
    sorting: false,
    cellType: 'WITH_META_LIST',
  },
  {
    name: 'gender',
    displayName: 'Gender',
    width: 180,
    resizable: true,
    comparator: (a, b) => a.gender.localeCompare(b.gender),
    cellType: 'STATUS_HINT',
    translate: (a) => ({
      title: a.gender,
      statusAppearance: a.gender === 'Female' ? 'alert' : 'success',
    }),
    filters: [
      { label: 'Male', value: 'male' },
      { label: 'Female', value: 'female' },
    ],
    onFilterChange: (a, filters) => {
      for (const filter of filters) {
        if (a.gender.toLowerCase() === filter) return true;
      }
      return false;
    },
  },
  {
    name: 'icon',
    displayName: 'Icon',
    width: 100,
    resizable: true,
    align: 'center',
    cellType: 'ICON',
    translate: () => ({
      icon: 'events',
    }),
  },
];


  const loaderSchema = [
    {
        "name": "name",
        "displayName": "Name",
        "width": "40%",
        "resizable": true,
        "tooltip": true,
        "separator": true,
        "filters": [
            {
                "label": "A-G",
                "value": "a-g"
            },
            {
                "label": "H-R",
                "value": "h-r"
            },
            {
                "label": "S-Z",
                "value": "s-z"
            }
        ],
        "cellType": "AVATAR_WITH_TEXT"
    },
    {
        "name": "email",
        "displayName": "Email",
        "width": 250,
        "resizable": true,
        "sorting": false,
        "cellType": "WITH_META_LIST"
    },
    {
        "name": "gender",
        "displayName": "Gender",
        "width": 180,
        "resizable": true,
        "cellType": "STATUS_HINT",
        "filters": [
            {
                "label": "Male",
                "value": "male"
            },
            {
                "label": "Female",
                "value": "female"
            }
        ]
    },
    {
        "name": "icon",
        "displayName": "Icon",
        "width": 100,
        "resizable": true,
        "align": "center",
        "cellType": "ICON"
    },
    {
        "name": "customCell",
        "displayName": "Custom Cell",
        "width": 200,
        "resizable": true,
        "cellType": "WITH_META_LIST"
    }
];

  return (
    <div
      className="vh-50"
    >
      <Card className="h-100 overflow-hidden">
        <Table
          loaderSchema={loaderSchema}
          data={data}
          schema={schema}
          withHeader={true}
          headerOptions={{
            withSearch: true
          }}
          onSearch={(currData, searchTerm) => {
            return currData.filter(d =>
              d.firstName.toLowerCase().match(searchTerm.toLowerCase())
              || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
            );
          }}
          withCheckbox={true}
          onSelect={(rowIndex, selected, selectedList, selectAll) => console.log(`on-select:- rowIndex: ${rowIndex} selected: ${selected} selectedList: ${JSON.stringify(selectedList)} selectAll: ${selectAll}`)}
          withPagination={true}
          pageSize={4}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
    </div>
  );
};

```


#### Custom Header Cell Renderer

```jsx
import { Icon, Badge, Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      claim_id: 'Q10000101',
      claim_type: 'Professional',
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "03/27/2020",
      last_dos: "03/30/2020",
      firstName: 'Brooke',
      lastName: 'Heeran',
    },
    {
      claim_id: 'Q10000102',
      claim_type: "Professional",
      plan_name: "MSSP Track 1",
      insurance_name: "Medicare",
      first_dos: "03/24/2020",
      last_dos: "04/30/2020",
      firstName: 'Frazer',
      lastName: 'Cathro',
    },
    {
      claim_id: 'Q10000103',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "05/16/2020",
      last_dos: "05/30/2020",
      firstName: 'Lemmie',
      lastName: 'Ciric',
    },
    {
      claim_id: 'Q10000104',
      claim_type: "Institutional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "12/27/2020",
      last_dos: "12/30/2020",
      firstName: 'Randy',
      lastName: 'Boatwright',
    },
    {
      claim_id: 'Q10000105',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "05/04/2020",
      last_dos: "05/28/2020",
      firstName: 'Rolando',
      lastName: 'Cyples',
    },
    {
      claim_id: 'Q10000106',
      claim_type: "Institutional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "01/27/2020",
      last_dos: "03/30/2020",
      firstName: 'Lem',
      lastName: 'Males',
    },
    {
      claim_id: 'Q10000107',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "03/30/2020",
      last_dos: "04/30/2020",
      firstName: 'Sayres',
      lastName: 'Adelberg',
    },
    {
      claim_id: 'Q10000108',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "02/27/2020",
      last_dos: "03/30/2020",
      firstName: 'Murray',
      lastName: 'Bravington',
    },
    {
      claim_id: 'Q10000109',
      claim_type: "Institutional",
      plan_name: "MSSP Track 5",
      insurance_name: "Medicare",
      first_dos: "03/17/2020",
      last_dos: "03/30/2020",
      firstName: 'Carin',
      lastName: 'Robiou',
    },
    {
      claim_id: 'Q100001010',
      claim_type: "Institutional",
      plan_name: "MSSP Track 6",
      insurance_name: "Medicare",
      first_dos: "09/27/2020",
      last_dos: "12/27/2020",
      firstName: 'Brina',
      lastName: 'Pirie',
    }
  ];

  const schema = [
    {
      name: 'claim_id',
      displayName: 'Claim Id',
      width: '12%',
      separator: true,
    },
    {
      name: 'claim_type',
      displayName: 'Claim Type',
      width: '15%',
      separator: true,
      cellType: "DEFAULT",
      headerCellRenderer: () => {
        return (
          <>
            <Icon name="info" />
            <Badge>Custom Header</Badge>
          </>
        )
      },
    },
    {
      name: 'insurance_name',
      displayName: 'Insurance Name',
      width: '15%',
      separator: true,
    },
    {
      name: 'plan_name',
      displayName: 'Plan Name',
      width: '15%',
      separator: true,
    },
    {
      name: 'first_dos',
      displayName: 'First Date of Service',
      width: '18%',
      separator: true,
    },
    {
      name: 'last_dos',
      displayName: 'Last Date of Service',
      width: '18%',
      separator: true,
    },
    {
      name: 'provider_name',
      displayName: 'Provider Name',
      separator: true,
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      translate: (a) => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
    },
  ];

  const loaderSchema = [
    {
        "name": "name",
        "displayName": "Name",
        "width": "40%",
        "resizable": true,
        "tooltip": true,
        "separator": true,
        "filters": [
            {
                "label": "A-G",
                "value": "a-g"
            },
            {
                "label": "H-R",
                "value": "h-r"
            },
            {
                "label": "S-Z",
                "value": "s-z"
            }
        ],
        "cellType": "AVATAR_WITH_TEXT"
    },
    {
        "name": "email",
        "displayName": "Email",
        "width": 250,
        "resizable": true,
        "sorting": false,
        "cellType": "WITH_META_LIST"
    },
    {
        "name": "gender",
        "displayName": "Gender",
        "width": 180,
        "resizable": true,
        "cellType": "STATUS_HINT",
        "filters": [
            {
                "label": "Male",
                "value": "male"
            },
            {
                "label": "Female",
                "value": "female"
            }
        ]
    },
    {
        "name": "icon",
        "displayName": "Icon",
        "width": 100,
        "resizable": true,
        "align": "center",
        "cellType": "ICON"
    },
    {
        "name": "customCell",
        "displayName": "Custom Cell",
        "width": 200,
        "resizable": true,
        "cellType": "WITH_META_LIST"
    }
];

  return (
      <Card className="overflow-hidden">
        <Table
          loaderSchema={loaderSchema}
          showMenu={false}
          separator={true}
          data={data}
          schema={schema}
          withHeader={true}
          pageSize={5}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
  );
}
```


#### Error State In Table

```jsx
import { EmptyState, Button, Card, Table } from '@innovaccer/design-system';

() => {
  // import noContent from '@innovaccer/mds-images/ui-states/404-nothing-here-3.svg';

  const schema = [
  {
    name: 'name',
    displayName: 'Name',
    width: '40%',
    resizable: true,
    tooltip: true,
    separator: true,
    translate: (a) => ({
      title: `${a.firstName} ${a.lastName}`,
      firstName: a.firstName,
      lastName: a.lastName,
    }),
    filters: [
      { label: 'A-G', value: 'a-g' },
      { label: 'H-R', value: 'h-r' },
      { label: 'S-Z', value: 's-z' },
    ],
    onFilterChange: (a, filters) => {
      for (const filter of filters) {
        switch (filter) {
          case 'a-g':
            if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
            break;
          case 'h-r':
            if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
            break;
          case 's-z':
            if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
            break;
        }
      }
      return false;
    },
    cellType: 'AVATAR_WITH_TEXT',
  },
  {
    name: 'email',
    displayName: 'Email',
    width: 250,
    resizable: true,
    sorting: false,
    cellType: 'WITH_META_LIST',
  },
  {
    name: 'gender',
    displayName: 'Gender',
    width: 180,
    resizable: true,
    comparator: (a, b) => a.gender.localeCompare(b.gender),
    cellType: 'STATUS_HINT',
    translate: (a) => ({
      title: a.gender,
      statusAppearance: a.gender === 'Female' ? 'alert' : 'success',
    }),
    filters: [
      { label: 'Male', value: 'male' },
      { label: 'Female', value: 'female' },
    ],
    onFilterChange: (a, filters) => {
      for (const filter of filters) {
        if (a.gender.toLowerCase() === filter) return true;
      }
      return false;
    },
  },
  {
    name: 'icon',
    displayName: 'Icon',
    width: 100,
    resizable: true,
    align: 'center',
    cellType: 'ICON',
    translate: () => ({
      icon: 'events',
    }),
  }
];

  const errorTemplate = () => {
    return (
      <EmptyState>
        <EmptyState.Image src={"static/media/404-nothing-here-3.2871b1b3.svg"}></EmptyState.Image>
        <EmptyState.Title>Failed to load data</EmptyState.Title>
        <EmptyState.Description>
          We are unable to fetch the data. Try again. If the issue persists, contact Innovaccer support.
        </EmptyState.Description>
        <EmptyState.Actions>
          <Button icon="refresh">Try again</Button>
        </EmptyState.Actions>
      </EmptyState>
    );
  };

  return (
    <div className="vh-75">
      <Card className="h-100 overflow-hidden">
        <Table data={[]} schema={schema} error={true} errorTemplate={errorTemplate} />
      </Card>
    </div>
  );
}
```


#### Async Table With Filters

```jsx
import {  } from '@innovaccer/design-system';

() => {
  return <></>;
}
```


#### Nested Table With Nested Cards

```jsx
import { Button, CardSubdued, Row, Column, Text, Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      "firstName": "Brooke",
      "lastName": "Heeran",
      lastRun: "Yesterday 3:14 PM",
      "name": "Risk Analysis",
      "type": "Batch Execution",
      status: "Failed",
      statusType: "Error",
      errorCode: 2204,
      className: "File not found",
      errorMessage: "Cannot fetch files"

    },
    {
      "firstName": "Frazer",
      "lastName": "Cathro",
      lastRun: "Yesterday 11:15 AM",
      "name": "Quality",
      "type": "Batch Execution",
      status: "Completed",
      statusType: "Done",
      className: "Executed",
    },
    {
      "firstName": "Lemmie",
      "lastName": "Ciric",
      lastRun: "Yesterday 9:17 PM",
      "name": "Claims",
      "type": "Test Function",
      status: "Completed",
      statusType: "Done",
      className: "Executed",
    },
    {
      firstName: 'Randy',
      lastName: 'Boatwright',
      lastRun: 'Yesterday 4:26 PM',
      name: 'Risk Analysis',
      type: 'Batch Execution',
      status: 'Completed',
      statusType: 'Done',
      className: 'Executed',
    },
    {
      firstName: 'Rolando',
      lastName: 'Cyples',
      lastRun: 'Yesterday 7:34 AM',
      name: 'Quality',
      type: 'Test Function',
      status: 'Failed',
      statusType: 'Error',
      errorCode: 2204,
      className: 'File not found',
      errorMessage: 'Cannot fetch files',
    },
  ];

  const schema = [
    {
      name: 'lastRun',
      displayName: 'Last Run',
      width: '25%',
    },
    {
      name: 'name',
      displayName: 'Name',
      width: '15%',
    },
    {
      name: 'type',
      displayName: 'Type',
      width: '20%',
    },
    {
      name: 'status',
      displayName: 'Status',
      width: '20%',
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.status,
        statusAppearance: (a.status === 'Failed') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Failed', value: 'failed' },
        { label: 'Completed', value: 'completed' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.status.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'user',
      displayName: 'User',
      width: '20%',
      translate: a => ({
        title: `${a.lastName}, ${a.firstName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      cellType: 'AVATAR_WITH_TEXT',
    },
  ];

  const onDataExport = (data) => {
    console.log('Exporting data', data);
  };

  const globalActionTrigger = (data) => {
    return (
      <div className="d-flex">
        <Button onClick={() => onDataExport(data)}>Export</Button>
        <Button className="ml-4" appearance="primary" onClick={() => onDataExport(data)}>
          Add to simulation
        </Button>
      </div>
    );
  };

  const nestedRowRenderer = (props) => {
    const {
      data,
      rowIndex
    } = props;
    if(rowIndex % 2){
      return false;
    }
    return (
      <CardSubdued className="mb-4 mt-3 mr-4 ml-9">
        <Row>
          <Column size={2}>
            <Text weight="medium">Type</Text> <br />
            <Text weight="medium">Error code</Text> <br />
            <Text weight="medium">Class name</Text> <br />
            <Text weight="medium">Error message</Text>
          </Column>
          <Column>
            <Text>{props.data.type}</Text> <br />
            <Text>{props.data.errorCode}</Text> <br />
            <Text>{props.data.className}</Text> <br />
            <Text>{props.data.errorMessage}</Text>
          </Column>
        </Row>
      </CardSubdued>
    );
  }

  return (
    <Card className="overflow-hidden">
      <Table
        data={data}
        schema={schema}
        withHeader={true}
        headerOptions={{
          withSearch: true,
          dynamicColumn: false,
          globalActionRenderer : globalActionTrigger
        }}
        separator={false}
        showMenu={false}
        nestedRows={true}
        filterPosition="HEADER"
        nestedRowRenderer={nestedRowRenderer}
        filterList={{
          status: ['failed', 'completed']
        }}
      />
    </Card>
  );
}
```


#### Nested Table With Nested Rows

```jsx
import { Button, Divider, List, Card, Table } from '@innovaccer/design-system';


() => {
  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: 300,
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
      cellType: 'WITH_META_LIST'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      separator: true,
      sorting: false,
      cellRenderer: (props) => {
        const {
          loading
        } = props;

        if (loading) return <></>;

        return (
          <Button appearance={'primary'}>Button</Button>
        );
      }
    },
  ];

  const nestedRowRenderer = (props) => {
    const {
      schema,
      data,
      loading,
      rowIndex,
      expanded
    } = props;

    if (rowIndex % 2) {
      return false;
    }
    return (
      <div>
        <Divider className='ml-5' />
        <List
          loading={loading}
          schema={schema}
          data={[data]}
        />
      </div>
    );
  }

  return (
    <div className="vh-75">
      <Card className="h-100 overflow-hidden">
        <Table
          data={data}
          schema={schema}
          nestedRows={true}
          nestedRowRenderer={nestedRowRenderer}
        />
      </Card>
    </div>
  );
};

```


#### Pinned Columns in Table

```jsx
import { Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      s_no: 1,
      empi: "P087636",
      first_name: "Joy",
      last_name: "Lawson",
      dob: "01/12/1982",
      gender: 'Female',
      facility: 'Charity Medical Clinic'
    },
    {
      s_no: 2,
      empi: "P087637",
      first_name: "Hannah",
      last_name: "Pop",
      dob: "01/11/1982",
      gender: 'Female',
      facility: 'Bancroft Medical Clinic'
    },
    {
      s_no: 3,
      empi: "P087638",
      first_name: "Lisa",
      last_name: "Sanchez",
      dob: "02/12/1981",
      gender: 'Female',
      facility: 'Lullaby Medical Clinic'
    },
    {
      s_no: 4,
      empi: "P087639",
      first_name: "Kathy",
      last_name: "Powell",
      dob: "01/10/1972",
      gender: 'Female',
      facility: 'Charity Medical Clinic'
    },
    {
      s_no: 5 ,
      empi: "P087631",
      first_name: "Dennis",
      last_name: "Lane",
      dob: "01/10/1982",
      gender: 'Male',
      facility: 'Lullaby Medical Clinic'
    },
  ];

  const schema = [
    {
      name: 's_no',
      displayName: 'S.no.',
      width: '5%',
      sorting: false,
      pinned: 'left'
    },
    {
      name: 'empi',
      displayName: 'EMPI',
      width: '10%',
      sorting: false,
      pinned: 'left'
    },
    {
      name: 'first_name',
      displayName: 'First Name',
      width: '20%',
      sorting: false
    },
    {
      name: 'last_name',
      displayName: 'Last Name',
      width: '20%',
      sorting: false
    },
    {
      name: 'dob',
      displayName: 'DOB',
      width: '20%',
      sorting: false
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: '20%',
      sorting: false
    },
    {
      name: 'facility',
      displayName: 'Facility',
      sorting: false
    },
  ];

  return (
      <Card className="overflow-hidden">
        <Table
          showMenu={false}
          size="compressed"
          separator={false}
          data={data}
          schema={schema}
          withHeader={true}
          headerOptions={{
            withSearch: false
          }}
          withPagination={false}
        />
      </Card>
  );
}
```


#### Selection Behavior in Table

```jsx
import { Icon, GridCell, Card, Table } from '@innovaccer/design-system';


() => {
  const translateData = (schema, data) => {
    let newData = data;

    if (schema.translate) {
      const translatedData = schema.translate(data);
      newData = {
        ...newData,
        [schema.name]: typeof translatedData === 'object' ? {
          ...newData[schema.name],
          ...translatedData
        } : translatedData
      };
    }
    if (typeof newData[schema.name] !== 'object') newData[schema.name] = { title: newData[schema.name] };

    return newData;
  }

  const filterData = (schema, data, filterList) => {
    let filteredData = data;
    if (filterList) {
      Object.keys(filterList).forEach(schemaName => {
        const filters = filterList[schemaName];
        const sIndex = schema.findIndex(s => s.name === schemaName);
        const { onFilterChange } = schema[sIndex];
        if (filters.length && onFilterChange) {
          filteredData = filteredData.filter(d => onFilterChange(d, filters));
        }
      });
    }

    return filteredData;
  };

  const sortData = (schema, data, sortingList) => {
    const sortedData = [...data];
    sortingList.forEach(l => {
      const sIndex = schema.findIndex(s => s.name === l.name);
      if (sIndex !== -1) {
        const defaultComparator = (a, b) => {
          const aData = translateData(schema[sIndex], a);
          const bData = translateData(schema[sIndex], b);
          return aData[l.name].title.localeCompare(bData[l.name].title);
        };

        const {
          comparator = defaultComparator
        } = schema[sIndex];

        sortedData.sort(comparator);
        if (l.type === 'desc') sortedData.reverse();
      }
    });

    return sortedData;
  };

  const paginateData = (data, page, pageSize) => {
    const start = (page - 1) * pageSize;
    const end = start + pageSize;
    const paginatedData = data.slice(start, end);
    return paginatedData;
  };

  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];
  const [formattedData, setFormattedData] = React.useState(data);

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: 300,
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
      cellType: 'WITH_META_LIST'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      cellType: 'WITH_META_LIST',
      sorting: false,
      cellRenderer: props => {
        return (
          <>
            <Icon className="mr-5" name="events" />
            <GridCell
              {...props}
              schema={{
                ...props.schema,
                name: 'email'
              }}
            />
          </>
        );
      }
    },
  ];

  const fetchData = (options) => {
    const {
      page,
      pageSize,
      sortingList,
      filterList,
      searchTerm
    } = options;

    const onSearch = (d, searchTerm = '') => {
      return (
        d.firstName.toLowerCase().match(searchTerm.toLowerCase())
        || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
      );

      return true;
    }

    const filteredData = filterData(schema, data, filterList);
    const searchedData = filteredData.filter(d => onSearch(d, searchTerm));
    const sortedData = sortData(schema, searchedData, sortingList);
    setFormattedData(sortedData);

    if (page && pageSize) {
      return new Promise(resolve => {
        window.setTimeout(() => {
          const start = (page - 1) * pageSize;
          const end = start + pageSize;
          const slicedData = sortedData.slice(start, end);
          resolve({
            searchTerm,
            schema,
            count: sortedData.length,
            data: slicedData,
          });
        }, 2000);
      });
    }

    return new Promise(resolve => {
      window.setTimeout(() => {
        resolve({
          searchTerm,
          schema,
          count: sortedData.length,
          data: sortedData,
        });
      }, 2000);
    });
  }

  const loaderSchema = [
    {
        "name": "name",
        "displayName": "Name",
        "width": "40%",
        "resizable": true,
        "tooltip": true,
        "separator": true,
        "filters": [
            {
                "label": "A-G",
                "value": "a-g"
            },
            {
                "label": "H-R",
                "value": "h-r"
            },
            {
                "label": "S-Z",
                "value": "s-z"
            }
        ],
        "cellType": "AVATAR_WITH_TEXT"
    },
    {
        "name": "email",
        "displayName": "Email",
        "width": 250,
        "resizable": true,
        "sorting": false,
        "cellType": "WITH_META_LIST"
    },
    {
        "name": "gender",
        "displayName": "Gender",
        "width": 180,
        "resizable": true,
        "cellType": "STATUS_HINT",
        "filters": [
            {
                "label": "Male",
                "value": "male"
            },
            {
                "label": "Female",
                "value": "female"
            }
        ]
    },
    {
        "name": "icon",
        "displayName": "Icon",
        "width": 100,
        "resizable": true,
        "align": "center",
        "cellType": "ICON"
    },
    {
        "name": "customCell",
        "displayName": "Custom Cell",
        "width": 200,
        "resizable": true,
        "cellType": "WITH_META_LIST"
    }
];

  return (
    <div>
      <Card className="h-100 overflow-hidden">
        <Table
          loaderSchema={loaderSchema}
          fetchData={fetchData}
          withHeader={true}
          uniqueColumnName="firstName"
          headerOptions={{
            withSearch: true,
            customSelectionLabel: 'user',
            allowSelectAll: true,
          }}
          withCheckbox={true}
          onSelect={(rowIndex, selected, selectedList, selectAll) => console.log(`on-select: - rowIndex: ${ rowIndex } selected: ${ selected } selectedList: ${ JSON.stringify(selectedList) } selectAll: ${ selectAll } `)}
          withPagination={true}
          pageSize={5}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
    </div>
  );
};

```


#### Table with Bulk Actions

```jsx
import { Icon, GridCell, Button, Card, Table } from '@innovaccer/design-system';


() => {
  const translateData = (schema, data) => {
    let newData = data;

    if (schema.translate) {
      const translatedData = schema.translate(data);
      newData = {
        ...newData,
        [schema.name]: typeof translatedData === 'object' ? {
          ...newData[schema.name],
          ...translatedData
        } : translatedData
      };
    }
    if (typeof newData[schema.name] !== 'object') newData[schema.name] = { title: newData[schema.name] };

    return newData;
  }

  const filterData = (schema, data, filterList) => {
    let filteredData = data;
    if (filterList) {
      Object.keys(filterList).forEach(schemaName => {
        const filters = filterList[schemaName];
        const sIndex = schema.findIndex(s => s.name === schemaName);
        const { onFilterChange } = schema[sIndex];
        if (filters.length && onFilterChange) {
          filteredData = filteredData.filter(d => onFilterChange(d, filters));
        }
      });
    }

    return filteredData;
  };

  const sortData = (schema, data, sortingList) => {
    const sortedData = [...data];
    sortingList.forEach(l => {
      const sIndex = schema.findIndex(s => s.name === l.name);
      if (sIndex !== -1) {
        const defaultComparator = (a, b) => {
          const aData = translateData(schema[sIndex], a);
          const bData = translateData(schema[sIndex], b);
          return aData[l.name].title.localeCompare(bData[l.name].title);
        };

        const {
          comparator = defaultComparator
        } = schema[sIndex];

        sortedData.sort(comparator);
        if (l.type === 'desc') sortedData.reverse();
      }
    });

    return sortedData;
  };

  const paginateData = (data, page, pageSize) => {
    const start = (page - 1) * pageSize;
    const end = start + pageSize;
    const paginatedData = data.slice(start, end);
    return paginatedData;
  };

  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];
  const [formattedData, setFormattedData] = React.useState(data);

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: 300,
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
      cellType: 'WITH_META_LIST'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      cellType: 'WITH_META_LIST',
      sorting: false,
      cellRenderer: props => {
        return (
          <>
            <Icon className="mr-5" name="events" />
            <GridCell
              {...props}
              schema={{
                ...props.schema,
                name: 'email'
              }}
            />
          </>
        );
      }
    },
  ];

  const fetchData = (options) => {
    const {
      page,
      pageSize,
      sortingList,
      filterList,
      searchTerm
    } = options;

    const onSearch = (d, searchTerm = '') => {
      return (
        d.firstName.toLowerCase().match(searchTerm.toLowerCase())
        || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
      );

      return true;
    }

    const filteredData = filterData(schema, data, filterList);
    const searchedData = filteredData.filter(d => onSearch(d, searchTerm));
    const sortedData = sortData(schema, searchedData, sortingList);
    setFormattedData(sortedData);

    if (page && pageSize) {
      return new Promise(resolve => {
        window.setTimeout(() => {
          const start = (page - 1) * pageSize;
          const end = start + pageSize;
          const slicedData = sortedData.slice(start, end);
          resolve({
            searchTerm,
            schema,
            count: sortedData.length,
            data: slicedData,
          });
        }, 2000);
      });
    }

    return new Promise(resolve => {
      window.setTimeout(() => {
        resolve({
          searchTerm,
          schema,
          count: sortedData.length,
          data: sortedData,
        });
      }, 2000);
    });
  }

  const loaderSchema = [
    {
        "name": "name",
        "displayName": "Name",
        "width": "40%",
        "resizable": true,
        "tooltip": true,
        "separator": true,
        "filters": [
            {
                "label": "A-G",
                "value": "a-g"
            },
            {
                "label": "H-R",
                "value": "h-r"
            },
            {
                "label": "S-Z",
                "value": "s-z"
            }
        ],
        "cellType": "AVATAR_WITH_TEXT"
    },
    {
        "name": "email",
        "displayName": "Email",
        "width": 250,
        "resizable": true,
        "sorting": false,
        "cellType": "WITH_META_LIST"
    },
    {
        "name": "gender",
        "displayName": "Gender",
        "width": 180,
        "resizable": true,
        "cellType": "STATUS_HINT",
        "filters": [
            {
                "label": "Male",
                "value": "male"
            },
            {
                "label": "Female",
                "value": "female"
            }
        ]
    },
    {
        "name": "icon",
        "displayName": "Icon",
        "width": 100,
        "resizable": true,
        "align": "center",
        "cellType": "ICON"
    },
    {
        "name": "customCell",
        "displayName": "Custom Cell",
        "width": 200,
        "resizable": true,
        "cellType": "WITH_META_LIST"
    }
];

  const onDataExport = (data) => {
    console.log("Exporting data", data);
  }

  const globalActionTrigger = (data) => {
    return (<Button onClick={() => onDataExport(data)}>Export</Button>);
  } 

  const selectionActionRenderer = (selectedData, selectAll) => {
    console.log('selectedData in output', selectedData, 'selectAll', selectAll);
    return (
      <div className="d-flex align-items-center">
        <Button size="tiny" className="mr-4">Delete</Button>
        <Button size="tiny">Export</Button>
      </div>
    )
  }

  return (
    <div>
      <Card className="h-100 overflow-hidden">
        <Table
          loaderSchema={loaderSchema}
          fetchData={fetchData}
          withHeader={true}
          uniqueColumnName="firstName"
          headerOptions={{
            selectionActionRenderer,
            withSearch: true,
            customSelectionLabel: 'user',
            globalActionRenderer : globalActionTrigger,
            allowSelectAll: true,
          }}
          withCheckbox={true}
          onSelect={(rowIndex, selected, selectedList, selectAll) => console.log(`on-select: - rowIndex: ${ rowIndex } selected: ${ selected } selectedList: ${ JSON.stringify(selectedList) } selectAll: ${ selectAll } `)}
          withPagination={true}
          pageSize={5}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
    </div>
  );
};

```


#### Table with Bulk Actions and Space Constraint

```jsx
import { Icon, GridCell, Button, Card, Table } from '@innovaccer/design-system';


() => {
  const translateData = (schema, data) => {
    let newData = data;

    if (schema.translate) {
      const translatedData = schema.translate(data);
      newData = {
        ...newData,
        [schema.name]: typeof translatedData === 'object' ? {
          ...newData[schema.name],
          ...translatedData
        } : translatedData
      };
    }
    if (typeof newData[schema.name] !== 'object') newData[schema.name] = { title: newData[schema.name] };

    return newData;
  }

  const filterData = (schema, data, filterList) => {
    let filteredData = data;
    if (filterList) {
      Object.keys(filterList).forEach(schemaName => {
        const filters = filterList[schemaName];
        const sIndex = schema.findIndex(s => s.name === schemaName);
        const { onFilterChange } = schema[sIndex];
        if (filters.length && onFilterChange) {
          filteredData = filteredData.filter(d => onFilterChange(d, filters));
        }
      });
    }

    return filteredData;
  };

  const sortData = (schema, data, sortingList) => {
    const sortedData = [...data];
    sortingList.forEach(l => {
      const sIndex = schema.findIndex(s => s.name === l.name);
      if (sIndex !== -1) {
        const defaultComparator = (a, b) => {
          const aData = translateData(schema[sIndex], a);
          const bData = translateData(schema[sIndex], b);
          return aData[l.name].title.localeCompare(bData[l.name].title);
        };

        const {
          comparator = defaultComparator
        } = schema[sIndex];

        sortedData.sort(comparator);
        if (l.type === 'desc') sortedData.reverse();
      }
    });

    return sortedData;
  };

  const paginateData = (data, page, pageSize) => {
    const start = (page - 1) * pageSize;
    const end = start + pageSize;
    const paginatedData = data.slice(start, end);
    return paginatedData;
  };

  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];
  const [formattedData, setFormattedData] = React.useState(data);

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: 300,
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
      cellType: 'WITH_META_LIST'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      cellType: 'WITH_META_LIST',
      sorting: false,
      cellRenderer: props => {
        return (
          <>
            <Icon className="mr-5" name="events" />
            <GridCell
              {...props}
              schema={{
                ...props.schema,
                name: 'email'
              }}
            />
          </>
        );
      }
    },
  ];

  const fetchData = (options) => {
    const {
      page,
      pageSize,
      sortingList,
      filterList,
      searchTerm
    } = options;

    const onSearch = (d, searchTerm = '') => {
      return (
        d.firstName.toLowerCase().match(searchTerm.toLowerCase())
        || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
      );

      return true;
    }

    const filteredData = filterData(schema, data, filterList);
    const searchedData = filteredData.filter(d => onSearch(d, searchTerm));
    const sortedData = sortData(schema, searchedData, sortingList);
    setFormattedData(sortedData);

    if (page && pageSize) {
      return new Promise(resolve => {
        window.setTimeout(() => {
          const start = (page - 1) * pageSize;
          const end = start + pageSize;
          const slicedData = sortedData.slice(start, end);
          resolve({
            searchTerm,
            schema,
            count: sortedData.length,
            data: slicedData,
          });
        }, 2000);
      });
    }

    return new Promise(resolve => {
      window.setTimeout(() => {
        resolve({
          searchTerm,
          schema,
          count: sortedData.length,
          data: sortedData,
        });
      }, 2000);
    });
  }

  const loaderSchema = [
    {
        "name": "name",
        "displayName": "Name",
        "width": "40%",
        "resizable": true,
        "tooltip": true,
        "separator": true,
        "filters": [
            {
                "label": "A-G",
                "value": "a-g"
            },
            {
                "label": "H-R",
                "value": "h-r"
            },
            {
                "label": "S-Z",
                "value": "s-z"
            }
        ],
        "cellType": "AVATAR_WITH_TEXT"
    },
    {
        "name": "email",
        "displayName": "Email",
        "width": 250,
        "resizable": true,
        "sorting": false,
        "cellType": "WITH_META_LIST"
    },
    {
        "name": "gender",
        "displayName": "Gender",
        "width": 180,
        "resizable": true,
        "cellType": "STATUS_HINT",
        "filters": [
            {
                "label": "Male",
                "value": "male"
            },
            {
                "label": "Female",
                "value": "female"
            }
        ]
    },
    {
        "name": "icon",
        "displayName": "Icon",
        "width": 100,
        "resizable": true,
        "align": "center",
        "cellType": "ICON"
    },
    {
        "name": "customCell",
        "displayName": "Custom Cell",
        "width": 200,
        "resizable": true,
        "cellType": "WITH_META_LIST"
    }
];

  const onDataExport = (data) => {
    console.log("Exporting data", data);
  }

  const globalActionTrigger = (data) => {
    return (<Button onClick={() => onDataExport(data)}>Export</Button>);
  } 

  const selectionActionRenderer = (selectedData, selectAll) => {
    console.log('selectedData in output', selectedData, 'selectAll', selectAll);
    return (
      <div className="d-flex align-items-center">
        <Button size="tiny" className="mr-4" icon="delete" tooltip='Delete' />
        <Button size="tiny" icon="content_paste" tooltip='Export' />
      </div>
    )
  }

  return (
    <div>
      <Card className="h-100 overflow-hidden">
        <Table
          loaderSchema={loaderSchema}
          fetchData={fetchData}
          withHeader={true}
          uniqueColumnName="firstName"
          headerOptions={{
            selectionActionRenderer,
            withSearch: true,
            customSelectionLabel: 'user',
            globalActionRenderer : globalActionTrigger,
            allowSelectAll: true,
          }}
          withCheckbox={true}
          onSelect={(rowIndex, selected, selectedList, selectAll) => console.log(`on-select: - rowIndex: ${ rowIndex } selected: ${ selected } selectedList: ${ JSON.stringify(selectedList) } selectAll: ${ selectAll } `)}
          withPagination={true}
          pageSize={5}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
    </div>
  );
};

```


#### Compressed Table

```jsx
import { Button, Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'MSSP Track 1 Urban',
      status: "Active",
      measures: 9,
      current_period: "March 2017 - Feb 2018",
      added_in: "March 2014",
    },
    {
      name: 'MSSP Track 1 Rural',
      status: "Active",
      measures: 9,
      current_period: "March 2017 - Feb 201",
      added_in: "March 2015",
    },
    {
      name: 'MSSP Track 2',
      status: "Inactive",
      measures: 14,
      current_period: "March 2017 - Feb 201",
      added_in: "March 2016",
    },
    {
      name: 'Aetna',
      status: "Active",
      measures: 20,
      current_period: "March 2017 - Feb 201",
      added_in: "March 2019",
    },
    {
      name: 'BCBS',
      status: "Active",
      measures: 16,
      current_period: "March 2017 - Feb 201",
      added_in: "March 2017",
    },
  ];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '20%',
      sorting: false
    },
    {
      name: 'status',
      displayName: 'Status',
      width: '20%',
      translate: a => ({
        title: a.status,
        statusAppearance: (a.status === 'Inactive') ? 'default' : 'success'
      }),
      cellType: "STATUS_HINT",
      sorting: false
    },
    {
      name: 'measures',
      displayName: 'No. of Measures',
      width: '20%',
      comparator: (a, b) => {
        if (a.measures < b.measures) {
          return -1;
        } else if (a.measures === b.measures) {
          return 0;
        } else {
          return 1;
        }
      },
      sorting: true
    },
    {
      name: 'current_period',
      displayName: 'Current Period',
      width: '20%',
      sorting: false
    },
    {
      name: 'added_in',
      displayName: 'Added in',
      width: '20%',
      sorting: false
    },
  ];

  const onDataExport = (data) => {
    console.log("Exporting data", data);
  }
  
  const globalActionTrigger = (data) => {
    return (<Button onClick={() => onDataExport(data)}>Export</Button>);
  } 

  return (
      <Card className="overflow-hidden">
        <Table
          showMenu={false}
          size="compressed"
          separator={false}
          data={data}
          schema={schema}
          withHeader={true}
          headerOptions={{
            withSearch: true,
            globalActionRenderer : globalActionTrigger
          }}
          onSearch={(currData, searchTerm) => {
            return currData.filter(d =>
              d.name.toLowerCase().match(searchTerm.toLowerCase())
            );
          }}
          withPagination={false}
        />
      </Card>
  );
}
```


#### Standard Table

```jsx
import { Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'MSSP Track 1 Urban',
      status: "Active",
      measures: "9",
      current_period: "March 2017 - Feb 2018",
      added_in: "March 2014",
    },
    {
      name: 'MSSP Track 1 Rural',
      status: "Active",
      measures: "9",
      current_period: "March 2017 - Feb 201",
      added_in: "March 2015",
    },
    {
      name: 'MSSP Track 2',
      status: "Inactive",
      measures: "14",
      current_period: "March 2017 - Feb 201",
      added_in: "March 2016",
    },
    {
      name: 'Aetna',
      status: "Active",
      measures: "20",
      current_period: "March 2017 - Feb 201",
      added_in: "March 2019",
    },
    {
      name: 'BCBS',
      status: "Active",
      measures: "16",
      current_period: "March 2017 - Feb 201",
      added_in: "March 2017",
    },
  ];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '20%',
      sorting: false
    },
    {
      name: 'status',
      displayName: 'Status',
      width: '20%',
      translate: a => ({
        title: a.status,
        statusAppearance: (a.status === 'Inactive') ? 'default' : 'success'
      }),
      cellType: "STATUS_HINT",
      sorting: false
    },
    {
      name: 'measures',
      displayName: 'No. of Measures',
      width: '20%',
      sorting: false
    },
    {
      name: 'current_period',
      displayName: 'Current Period',
      width: '20%',
      sorting: false
    },
    {
      name: 'added_in',
      displayName: 'Added in',
      width: '20%',
      sorting: false
    },
  ];

  return (
      <Card className="overflow-hidden">
        <Table
          showMenu={false}
          separator={false}
          data={data}
          schema={schema}
          withHeader={true}
          headerOptions={{
            withSearch: true
          }}
          onSearch={(currData, searchTerm) => {
            return currData.filter(d =>
              d.name.toLowerCase().match(searchTerm.toLowerCase())
            );
          }}
          withPagination={false}
        />
      </Card>
  );
}
```


#### Tight Table

```jsx
import { Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'MSSP Track 1 Urban',
      status: "Active",
      measures: "9",
      current_period: "March 2017 - Feb 2018",
      added_in: "March 2014",
    },
    {
      name: 'MSSP Track 1 Rural',
      status: "Active",
      measures: "9",
      current_period: "March 2017 - Feb 201",
      added_in: "March 2015",
    },
    {
      name: 'MSSP Track 2',
      status: "Inactive",
      measures: "14",
      current_period: "March 2017 - Feb 201",
      added_in: "March 2016",
    },
    {
      name: 'Aetna',
      status: "Active",
      measures: "20",
      current_period: "March 2017 - Feb 201",
      added_in: "March 2019",
    },
    {
      name: 'BCBS',
      status: "Active",
      measures: "16",
      current_period: "March 2017 - Feb 201",
      added_in: "March 2017",
    },
  ];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '20%',
      sorting: false
    },
    {
      name: 'status',
      displayName: 'Status',
      width: '20%',
      translate: a => ({
        title: a.status,
        statusAppearance: (a.status === 'Inactive') ? 'default' : 'success'
      }),
      cellType: "STATUS_HINT",
      sorting: false
    },
    {
      name: 'measures',
      displayName: 'No. of Measures',
      width: '20%',
      sorting: false
    },
    {
      name: 'current_period',
      displayName: 'Current Period',
      width: '20%',
      sorting: false
    },
    {
      name: 'added_in',
      displayName: 'Added in',
      width: '20%',
      sorting: false
    },
  ];

  return (
      <Card className="overflow-hidden">
        <Table
          showMenu={false}
          size="tight"
          separator={false}
          data={data}
          schema={schema}
          withHeader={true}
          headerOptions={{
            withSearch: true
          }}
          onSearch={(currData, searchTerm) => {
            return currData.filter(d =>
              d.name.toLowerCase().match(searchTerm.toLowerCase())
            );
          }}
          withPagination={false}
        />
      </Card>
  );
}
```


#### States in Data table

```jsx
import { Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      claim_id: 'Q10000101',
      claim_type: 'Professional',
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "03/27/2020",
      last_dos: "03/30/2020",
      firstName: 'Brooke',
      lastName: 'Heeran',
      disabled: true,
    },
    {
      claim_id: 'Q10000102',
      claim_type: "Professional",
      plan_name: "MSSP Track 1",
      insurance_name: "Medicare",
      first_dos: "03/24/2020",
      last_dos: "04/30/2020",
      firstName: 'Frazer',
      lastName: 'Cathro',
    },
    {
      claim_id: 'Q10000103',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "05/16/2020",
      last_dos: "05/30/2020",
      firstName: 'Lemmie',
      lastName: 'Ciric',
      disabled: true,
    },
    {
      claim_id: 'Q10000104',
      claim_type: "Institutional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "12/27/2020",
      last_dos: "12/30/2020",
      firstName: 'Randy',
      lastName: 'Boatwright',
    },
    {
      claim_id: 'Q10000105',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "05/04/2020",
      last_dos: "05/28/2020",
      firstName: 'Rolando',
      lastName: 'Cyples',
    },
    {
      claim_id: 'Q10000106',
      claim_type: "Institutional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "01/27/2020",
      last_dos: "03/30/2020",
      firstName: 'Lem',
      lastName: 'Males',
    },
    {
      claim_id: 'Q10000107',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "03/30/2020",
      last_dos: "04/30/2020",
      firstName: 'Sayres',
      lastName: 'Adelberg',
    },
    {
      claim_id: 'Q10000108',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "02/27/2020",
      last_dos: "03/30/2020",
      firstName: 'Murray',
      lastName: 'Bravington',
    },
    {
      claim_id: 'Q10000109',
      claim_type: "Institutional",
      plan_name: "MSSP Track 5",
      insurance_name: "Medicare",
      first_dos: "03/17/2020",
      last_dos: "03/30/2020",
      firstName: 'Carin',
      lastName: 'Robiou',
    },
    {
      claim_id: 'Q100001010',
      claim_type: "Institutional",
      plan_name: "MSSP Track 6",
      insurance_name: "Medicare",
      first_dos: "09/27/2020",
      last_dos: "12/27/2020",
      firstName: 'Brina',
      lastName: 'Pirie',
    }
  ];

  const schema = [
    {
      name: 'claim_id',
      displayName: 'Claim Id',
      width: '12%',
      separator: true,
    },
    {
      name: 'claim_type',
      displayName: 'Claim Type',
      width: '15%',
      separator: true,
      cellType: "DEFAULT"
    },
    {
      name: 'insurance_name',
      displayName: 'Insurance Name',
      width: '15%',
      separator: true,
    },
    {
      name: 'plan_name',
      displayName: 'Plan Name',
      width: '15%',
      separator: true,
    },
    {
      name: 'first_dos',
      displayName: 'First Date of Service',
      width: '18%',
      separator: true,
    },
    {
      name: 'last_dos',
      displayName: 'Last Date of Service',
      width: '18%',
      separator: true,
    },
    {
      name: 'provider_name',
      displayName: 'Provider Name',
      separator: true,
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      translate: (a) => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
    },
  ];

  const loaderSchema = [
    {
        "name": "name",
        "displayName": "Name",
        "width": "40%",
        "resizable": true,
        "tooltip": true,
        "separator": true,
        "filters": [
            {
                "label": "A-G",
                "value": "a-g"
            },
            {
                "label": "H-R",
                "value": "h-r"
            },
            {
                "label": "S-Z",
                "value": "s-z"
            }
        ],
        "cellType": "AVATAR_WITH_TEXT"
    },
    {
        "name": "email",
        "displayName": "Email",
        "width": 250,
        "resizable": true,
        "sorting": false,
        "cellType": "WITH_META_LIST"
    },
    {
        "name": "gender",
        "displayName": "Gender",
        "width": 180,
        "resizable": true,
        "cellType": "STATUS_HINT",
        "filters": [
            {
                "label": "Male",
                "value": "male"
            },
            {
                "label": "Female",
                "value": "female"
            }
        ]
    },
    {
        "name": "icon",
        "displayName": "Icon",
        "width": 100,
        "resizable": true,
        "align": "center",
        "cellType": "ICON"
    },
    {
        "name": "customCell",
        "displayName": "Custom Cell",
        "width": 200,
        "resizable": true,
        "cellType": "WITH_META_LIST"
    }
];

  return (
      <Card className="overflow-hidden">
        <Table
          loaderSchema={loaderSchema}
          showMenu={false}
          separator={true}
          data={data}
          schema={schema}
          withHeader={true}
          headerOptions={{
            withSearch: true
          }}
          onSearch={(currData, searchTerm) => {
            return currData.filter(d =>
              d.firstName.toLowerCase().match(searchTerm.toLowerCase())
              || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
              || d.claim_id.toLowerCase().match(searchTerm.toLowerCase())
            );
          }}
          withPagination={true}
          pageSize={5}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
  );
}
```


#### Disabled Row In Table

```jsx
import { Card, Table } from '@innovaccer/design-system';

() => {

  const data = [
    {
      "firstName": "Brooke",
      "lastName": "Heeran",
      lastRun: "Yesterday 3:14 PM",
      "name": "Risk Analysis",
      "type": "Batch Execution",
      status: "Failed",
      statusType: "Error",
      errorCode: 2204,
      className: "File not found",
      errorMessage: "Cannot fetch files",
      disabled: true,
    },
    {
      "firstName": "Frazer",
      "lastName": "Cathro",
      lastRun: "Yesterday 11:15 AM",
      "name": "Quality",
      "type": "Batch Execution",
      status: "Completed",
      statusType: "Done",
      className: "Executed",
    },
    {
      "firstName": "Lemmie",
      "lastName": "Ciric",
      lastRun: "Yesterday 9:17 PM",
      "name": "Claims",
      "type": "Test Function",
      status: "Completed",
      statusType: "Done",
      className: "Executed",
      disabled: true,
    },
    {
      firstName: 'Randy',
      lastName: 'Boatwright',
      lastRun: 'Yesterday 4:26 PM',
      name: 'Risk Analysis',
      type: 'Batch Execution',
      status: 'Completed',
      statusType: 'Done',
      className: 'Executed',
    },
    {
      firstName: 'Rolando',
      lastName: 'Cyples',
      lastRun: 'Yesterday 7:34 AM',
      name: 'Quality',
      type: 'Test Function',
      status: 'Failed',
      statusType: 'Error',
      errorCode: 2204,
      className: 'File not found',
      errorMessage: 'Cannot fetch files',
    },
  ];

  const schema = [
    {
      name: 'lastRun',
      displayName: 'Last Run',
      width: '25%',
    },
    {
      name: 'name',
      displayName: 'Name',
      width: '15%',
    },
    {
      name: 'type',
      displayName: 'Type',
      width: '20%',
    },
    {
      name: 'status',
      displayName: 'Status',
      width: '20%',
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.status,
        statusAppearance: (a.status === 'Failed') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Failed', value: 'failed' },
        { label: 'Completed', value: 'completed' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.status.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'user',
      displayName: 'User',
      width: '20%',
      translate: a => ({
        title: `${a.lastName}, ${a.firstName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      cellType: 'AVATAR_WITH_TEXT',
    },
  ];

  return (
      <Card className="overflow-hidden">
        <Table
          showMenu={false}
          size="compressed"
          separator={false}
          data={data}
          schema={schema}
          withHeader={true}
          withCheckbox={true}
          headerOptions={{
            withSearch: true
          }}
          onSearch={(currData, searchTerm) => {
            return currData.filter(record =>
              record.name.toLowerCase().match(searchTerm.toLowerCase())
            );
          }}
          onSelect={(rowIndex, selected, selectedList, selectAll) =>
            console.log(`on-select:- rowIndex: ${rowIndex} selected: ${selected} selectedList: ${JSON.stringify(selectedList)} selectAll: ${selectAll}`)
          }
          withPagination={false}
        />
      </Card>
  );
}
```


#### Loading State in Table

```jsx
import { Card, Table } from '@innovaccer/design-system';

() => {
  const loading = true;
  const pageSize = 5;
  const withCheckbox = true;

  return (
    <div className="vh-50">
      <Card className="h-100 overflow-hidden">
        <Table
          loading={loading}
          pageSize={pageSize}
          withCheckbox={withCheckbox}
          loaderSchema={loaderSchema}
          data={[]}
          schema={[]}
          showMenu={true}
          withHeader={true}
          headerOptions={{
            withSearch: true,
          }}
        />
      </Card>
    </div>
  );
}
```


#### States in Resource Table

```jsx
import { Avatar, Menu, Text, Card, Table } from '@innovaccer/design-system';


() => {
  const data = [
    {
        "name": "Asthma Outreach",
        "firstName": "Brooke",
        "lastName": "Heeran",
        "status": "In Progress",
        "lastUpdated": "June 20, 2020",
        "recipients": 11846,
        "_selected": true
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "status": "Scheduled",
        "lastUpdated": "June 19, 2020",
        "name": "HbA1c Test due",
        "recipients": 12846
    },
    {
        "firstName": "Lemmie",
        "name": "ER Education",
        "lastName": "Ciric",
        "status": "Draft",
        "lastUpdated": "May 19, 2020",
        "recipients": 118467,
        "_selected": true
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "name": "Flu Vaccination",
        "status": "Failed",
        "lastUpdated": "March 19, 2020",
        "recipients": 10846
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "name": "Well-child Visit",
        "status": "In Progress",
        "lastUpdated": "April 19, 2020",
        "recipients": 11847
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "name": "Annual wellness Visit",
        "status": "In Progress",
        "lastUpdated": "June 16, 2020",
        "recipients": 118100
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "name": "Flu Vaccination",
        "status": "Draft",
        "lastUpdated": "Dec 19, 2020",
        "recipients": 11848
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "name": "Well-child Visit",
        "status": "Draft",
        "lastUpdated": "April 19, 2020",
        "recipients": 11890
    }
];

  const statusAppearance = {
    'In Progress': 'info',
    'Scheduled': 'warning',
    'Draft': 'default',
    'Failed': 'alert'
  };

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '30%',
      cellType: 'WITH_META_LIST',
      sorting: false,
      translate: a => ({
        title: a.name,
        metaList: [`${a.recipients} recipients`]
      }),
    },
    {
      name: 'status',
      displayName: 'Status',
      width: '20%',
      cellType: 'STATUS_HINT',
      sorting: false,
      filters: [
        { label: 'In Progress', value: 'In Progress' },
        { label: 'Scheduled', value: 'Scheduled' },
        { label: 'Draft', value: 'Draft' },
        { label: 'Failed', value: 'Failed' }
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.status === filter) return true;
        }
        return false;
      },
      translate: a => {
        const status = a.status;
        return ({
          title: status,
          statusAppearance: statusAppearance[status]
        });
      }
    },
    {
      name: 'lastUpdated',
      displayName: 'Last Updated on',
      width: '30%',
      sorting: false,
    },
    {
      name: 'user',
      displayName: '',
      sorting: false,
      width: '20%',
      cellRenderer: (props) => {
        const { data } = props;
        return (
          <div className="d-flex align-items-center justify-content-end flex-grow-1">
            <Avatar firstName={data.firstName} lastName={data.lastName} />
            <div className="ml-6">
              <Menu trigger={<Menu.Trigger appearance="transparent" />}>
                <Menu.List>
                  <Menu.Item>
                    <Text>Edit</Text>
                  </Menu.Item>
                  <Menu.Item>
                    <Text>Delete</Text>
                  </Menu.Item>
                </Menu.List>
              </Menu>
            </div>
          </div>
        );
      }
    }
  ];

  return (
    <Card className="overflow-hidden">
      <Table
        showMenu={false}
        type="resource"
        data={data}
        schema={schema}
        withHeader={true}
        withCheckbox={true}
        filterPosition="HEADER"
        onSelect={(rowIndex, selected, selectedList, selectAll) =>
          console.log(`on-select:- rowIndex: ${rowIndex} selected: ${selected} selectedList: ${JSON.stringify(selectedList)} selectAll: ${selectAll}`)
        }
        headerOptions={{
          withSearch: true
        }}
        filterList={{
          status: ['In Progress', 'Scheduled', 'Draft', 'Failed']
        }}
        onSearch={(currData, searchTerm) => {
          return currData.filter(d =>
            d.firstName.toLowerCase().match(searchTerm.toLowerCase())
            || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
            || d.name.toLowerCase().match(searchTerm.toLowerCase())
          );
        }}
        withPagination={true}
        paginationType="basic"
        pageSize={4}
        onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
      />
    </Card>
  );
};

```


#### Sync Table

```jsx
import { Icon, GridCell, Button, Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '40%',
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
      cellType: 'WITH_META_LIST'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      cellType: 'WITH_META_LIST',
      sorting: false,
      cellRenderer: props => {
        return (
          <>
            <Icon className="mr-5" name="events" />
            <GridCell
              {...props}
              schema={{
                ...props.schema,
                name: 'email'
              }}
            />
          </>
        );
      }
    },
  ];

  const [error, setError] = React.useState(false);

  const onDataExport = (data) => {
    console.log("Exporting data", data);
  }

  const globalActionTrigger = (data) => {
    return (<Button onClick={() => onDataExport(data)}>Export</Button>);
  } 

  return (
    <div className="vh-75">
      <Card className="h-100 overflow-hidden">
        <Table
          error={error}
          data={data}
          schema={schema}
          withHeader={true}
          uniqueColumnName="email"
          headerOptions={{
            withSearch: true,
            globalActionRenderer : globalActionTrigger,
            allowSelectAll: true,
          }}
          onSearch={(currData, searchTerm) => {
            console.log('onsearch called', searchTerm);
            setError(!error);
            return currData.filter(d =>
              d.firstName.toLowerCase().match(searchTerm.toLowerCase())
              || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
            );
          }}
          withCheckbox={true}
          onSelect={(rowIndex, selected, selectedList, selectAll) => console.log(`on-select:- rowIndex: ${rowIndex} selected: ${selected} selectedList: ${JSON.stringify(selectedList)} selectAll: ${selectAll}`)}
          withPagination={true}
          pageSize={50}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
    </div>
  );
};

```


#### Toggle Option For Header Cell Menu

```jsx
import { Row, Column, Heading, Card, Table } from '@innovaccer/design-system';


() => {
  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Carin",
        "lastName": "Robiou",
        "email": "crobioua@skype.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Anson",
        "lastName": "Gamon",
        "email": "agamonb@economist.com",
        "gender": "Male"
    },
    {
        "firstName": "Brina",
        "lastName": "Pirie",
        "email": "bpiriec@stumbleupon.com",
        "gender": "Female"
    },
    {
        "firstName": "Hermy",
        "lastName": "Dyett",
        "email": "hdyettd@boston.com",
        "gender": "Male"
    },
    {
        "firstName": "Aime",
        "lastName": "von Hagt",
        "email": "avonhagte@nyu.edu",
        "gender": "Female"
    },
    {
        "firstName": "Gusti",
        "lastName": "Haycock",
        "email": "ghaycockf@virginia.edu",
        "gender": "Female"
    },
    {
        "firstName": "Mortimer",
        "lastName": "Kunneke",
        "email": "mkunnekeg@weather.com",
        "gender": "Male"
    },
    {
        "firstName": "Barnie",
        "lastName": "Pohls",
        "email": "bpohlsh@columbia.edu",
        "gender": "Male"
    },
    {
        "firstName": "Elliot",
        "lastName": "Nealey",
        "email": "enealeyi@cocolog-nifty.com",
        "gender": "Male"
    },
    {
        "firstName": "Allsun",
        "lastName": "Gong",
        "email": "agongj@discuz.net",
        "gender": "Female"
    },
    {
        "firstName": "Harwell",
        "lastName": "Kegan",
        "email": "hkegank@domainmarket.com",
        "gender": "Male"
    },
    {
        "firstName": "Gilles",
        "lastName": "Sandell",
        "email": "gsandelll@apache.org",
        "gender": "Male"
    },
    {
        "firstName": "Hilliard",
        "lastName": "Beamish",
        "email": "hbeamishm@shop-pro.jp",
        "gender": "Male"
    },
    {
        "firstName": "Charley",
        "lastName": "Kuschek",
        "email": "ckuschekn@dropbox.com",
        "gender": "Male"
    },
    {
        "firstName": "Danny",
        "lastName": "Churchin",
        "email": "dchurchino@bbc.co.uk",
        "gender": "Female"
    },
    {
        "firstName": "Ervin",
        "lastName": "Chatelain",
        "email": "echatelainp@mac.com",
        "gender": "Male"
    },
    {
        "firstName": "Milli",
        "lastName": "Joseph",
        "email": "mjosephq@merriam-webster.com",
        "gender": "Female"
    },
    {
        "firstName": "Greer",
        "lastName": "O'Doherty",
        "email": "godohertyr@homestead.com",
        "gender": "Female"
    },
    {
        "firstName": "Haroun",
        "lastName": "Martensen",
        "email": "hmartensens@skype.com",
        "gender": "Male"
    },
    {
        "firstName": "Desiree",
        "lastName": "Colwell",
        "email": "dcolwellt@businessinsider.com",
        "gender": "Female"
    },
    {
        "firstName": "Almeda",
        "lastName": "Jowsey",
        "email": "ajowseyu@ask.com",
        "gender": "Female"
    },
    {
        "firstName": "Cinderella",
        "lastName": "Dunnet",
        "email": "cdunnetv@mac.com",
        "gender": "Female"
    },
    {
        "firstName": "Hubert",
        "lastName": "Legion",
        "email": "hlegionw@ameblo.jp",
        "gender": "Male"
    },
    {
        "firstName": "Costa",
        "lastName": "Adamovsky",
        "email": "cadamovskyx@joomla.org",
        "gender": "Male"
    },
    {
        "firstName": "Kristan",
        "lastName": "Bielfeld",
        "email": "kbielfeldy@live.com",
        "gender": "Female"
    },
    {
        "firstName": "Sammy",
        "lastName": "Shermore",
        "email": "sshermorez@washington.edu",
        "gender": "Female"
    },
    {
        "firstName": "Kathi",
        "lastName": "Dowyer",
        "email": "kdowyer10@bluehost.com",
        "gender": "Female"
    },
    {
        "firstName": "Kennith",
        "lastName": "Whitehouse",
        "email": "kwhitehouse11@cornell.edu",
        "gender": "Male"
    },
    {
        "firstName": "Brianna",
        "lastName": "Garland",
        "email": "bgarland12@wikipedia.org",
        "gender": "Female"
    },
    {
        "firstName": "Cristobal",
        "lastName": "Mapholm",
        "email": "cmapholm13@constantcontact.com",
        "gender": "Male"
    },
    {
        "firstName": "Zia",
        "lastName": "Harrowing",
        "email": "zharrowing14@huffingtonpost.com",
        "gender": "Female"
    },
    {
        "firstName": "Zabrina",
        "lastName": "Gravener",
        "email": "zgravener15@ameblo.jp",
        "gender": "Female"
    },
    {
        "firstName": "Gregoor",
        "lastName": "Cruz",
        "email": "gcruz16@uol.com.br",
        "gender": "Male"
    },
    {
        "firstName": "Julita",
        "lastName": "Gemeau",
        "email": "jgemeau17@bandcamp.com",
        "gender": "Female"
    },
    {
        "firstName": "Gilbert",
        "lastName": "Sallier",
        "email": "gsallier18@dailymail.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Bride",
        "lastName": "Boniface",
        "email": "bboniface19@howstuffworks.com",
        "gender": "Female"
    },
    {
        "firstName": "Rodolph",
        "lastName": "Mattussevich",
        "email": "rmattussevich1a@nymag.com",
        "gender": "Male"
    },
    {
        "firstName": "Rowan",
        "lastName": "Rizon",
        "email": "rrizon1b@thetimes.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Avie",
        "lastName": "Nicolls",
        "email": "anicolls1c@nbcnews.com",
        "gender": "Female"
    },
    {
        "firstName": "Bram",
        "lastName": "Kleinhaut",
        "email": "bkleinhaut1d@imdb.com",
        "gender": "Male"
    },
    {
        "firstName": "Carmita",
        "lastName": "Costin",
        "email": "ccostin1e@hibu.com",
        "gender": "Female"
    },
    {
        "firstName": "Wash",
        "lastName": "Vannuchi",
        "email": "wvannuchi1f@japanpost.jp",
        "gender": "Male"
    },
    {
        "firstName": "Nikki",
        "lastName": "Faye",
        "email": "nfaye1g@feedburner.com",
        "gender": "Female"
    },
    {
        "firstName": "Aron",
        "lastName": "Scimonelli",
        "email": "ascimonelli1h@nationalgeographic.com",
        "gender": "Male"
    },
    {
        "firstName": "Smitty",
        "lastName": "Giacomello",
        "email": "sgiacomello1i@google.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Staci",
        "lastName": "D'Elias",
        "email": "sdelias1j@paginegialle.it",
        "gender": "Female"
    },
    {
        "firstName": "Radcliffe",
        "lastName": "Garbutt",
        "email": "rgarbutt1k@thetimes.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Maxwell",
        "lastName": "Krikorian",
        "email": "mkrikorian1l@ask.com",
        "gender": "Male"
    },
    {
        "firstName": "Dunstan",
        "lastName": "Chansonne",
        "email": "dchansonne1m@posterous.com",
        "gender": "Male"
    },
    {
        "firstName": "Isaak",
        "lastName": "Faherty",
        "email": "ifaherty1n@who.int",
        "gender": "Male"
    },
    {
        "firstName": "Sawyere",
        "lastName": "Ede",
        "email": "sede1o@drupal.org",
        "gender": "Male"
    },
    {
        "firstName": "Perren",
        "lastName": "Daddow",
        "email": "pdaddow1p@indiegogo.com",
        "gender": "Male"
    },
    {
        "firstName": "Brendis",
        "lastName": "Napier",
        "email": "bnapier1q@multiply.com",
        "gender": "Male"
    },
    {
        "firstName": "Francene",
        "lastName": "Godbold",
        "email": "fgodbold1r@joomla.org",
        "gender": "Female"
    },
    {
        "firstName": "Moll",
        "lastName": "Fludgate",
        "email": "mfludgate1s@who.int",
        "gender": "Female"
    },
    {
        "firstName": "Allayne",
        "lastName": "Medhurst",
        "email": "amedhurst1t@is.gd",
        "gender": "Male"
    },
    {
        "firstName": "Genvieve",
        "lastName": "Mellows",
        "email": "gmellows1u@stumbleupon.com",
        "gender": "Female"
    },
    {
        "firstName": "Rebe",
        "lastName": "Durnford",
        "email": "rdurnford1v@biglobe.ne.jp",
        "gender": "Female"
    },
    {
        "firstName": "Thalia",
        "lastName": "Joerning",
        "email": "tjoerning1w@netscape.com",
        "gender": "Female"
    },
    {
        "firstName": "Beckie",
        "lastName": "Lammin",
        "email": "blammin1x@gnu.org",
        "gender": "Female"
    },
    {
        "firstName": "Kassandra",
        "lastName": "Furney",
        "email": "kfurney1y@surveymonkey.com",
        "gender": "Female"
    },
    {
        "firstName": "Libbie",
        "lastName": "Gladyer",
        "email": "lgladyer1z@dropbox.com",
        "gender": "Female"
    },
    {
        "firstName": "Kai",
        "lastName": "Goldsbury",
        "email": "kgoldsbury20@census.gov",
        "gender": "Female"
    },
    {
        "firstName": "Arielle",
        "lastName": "De Bell",
        "email": "adebell21@addthis.com",
        "gender": "Female"
    },
    {
        "firstName": "Ellary",
        "lastName": "Warnock",
        "email": "ewarnock22@ted.com",
        "gender": "Male"
    },
    {
        "firstName": "Skelly",
        "lastName": "Blakes",
        "email": "sblakes23@reddit.com",
        "gender": "Male"
    },
    {
        "firstName": "Roanne",
        "lastName": "Stanyforth",
        "email": "rstanyforth24@com.com",
        "gender": "Female"
    },
    {
        "firstName": "Cash",
        "lastName": "Fettis",
        "email": "cfettis25@go.com",
        "gender": "Male"
    },
    {
        "firstName": "Farleigh",
        "lastName": "McDavid",
        "email": "fmcdavid26@sbwire.com",
        "gender": "Male"
    },
    {
        "firstName": "Holly",
        "lastName": "Barfford",
        "email": "hbarfford27@wsj.com",
        "gender": "Female"
    },
    {
        "firstName": "Hurley",
        "lastName": "Benaine",
        "email": "hbenaine28@sun.com",
        "gender": "Male"
    },
    {
        "firstName": "Maryjo",
        "lastName": "Gilhooly",
        "email": "mgilhooly29@tripod.com",
        "gender": "Female"
    },
    {
        "firstName": "Annis",
        "lastName": "Linkie",
        "email": "alinkie2a@wp.com",
        "gender": "Female"
    },
    {
        "firstName": "Mariel",
        "lastName": "Husher",
        "email": "mhusher2b@etsy.com",
        "gender": "Female"
    },
    {
        "firstName": "Niels",
        "lastName": "Klimontovich",
        "email": "nklimontovich2c@surveymonkey.com",
        "gender": "Male"
    },
    {
        "firstName": "Udall",
        "lastName": "Linfitt",
        "email": "ulinfitt2d@toplist.cz",
        "gender": "Male"
    },
    {
        "firstName": "Isidore",
        "lastName": "Kuhn",
        "email": "ikuhn2e@cdc.gov",
        "gender": "Male"
    },
    {
        "firstName": "Rosemonde",
        "lastName": "Kettle",
        "email": "rkettle2f@techcrunch.com",
        "gender": "Female"
    },
    {
        "firstName": "Cass",
        "lastName": "Boot",
        "email": "cboot2g@furl.net",
        "gender": "Male"
    },
    {
        "firstName": "Montague",
        "lastName": "Rossey",
        "email": "mrossey2h@goo.gl",
        "gender": "Male"
    },
    {
        "firstName": "Geno",
        "lastName": "Jenkyn",
        "email": "gjenkyn2i@opensource.org",
        "gender": "Male"
    },
    {
        "firstName": "Esdras",
        "lastName": "Skivington",
        "email": "eskivington2j@answers.com",
        "gender": "Male"
    },
    {
        "firstName": "Gabriello",
        "lastName": "Luce",
        "email": "gluce2k@nydailynews.com",
        "gender": "Male"
    },
    {
        "firstName": "Magdalene",
        "lastName": "Ilyunin",
        "email": "milyunin2l@prweb.com",
        "gender": "Female"
    },
    {
        "firstName": "Isidro",
        "lastName": "Fawson",
        "email": "ifawson2m@squidoo.com",
        "gender": "Male"
    },
    {
        "firstName": "Blinny",
        "lastName": "Palfrey",
        "email": "bpalfrey2n@networksolutions.com",
        "gender": "Female"
    },
    {
        "firstName": "Justen",
        "lastName": "Kordas",
        "email": "jkordas2o@symantec.com",
        "gender": "Male"
    },
    {
        "firstName": "Damien",
        "lastName": "Hallede",
        "email": "dhallede2p@unicef.org",
        "gender": "Male"
    },
    {
        "firstName": "Jaquelyn",
        "lastName": "Rockhall",
        "email": "jrockhall2q@vkontakte.ru",
        "gender": "Female"
    },
    {
        "firstName": "Garrek",
        "lastName": "Matignon",
        "email": "gmatignon2r@noaa.gov",
        "gender": "Male"
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
    },
  ];

  const values = [true, false];

  return (
    <div className="d-flex flex-wrap">
    <Row>
    {values.map((v, index) => (
      <Column size={5} key={index} className="ml-10">
        <Heading>{`showMenu: ${v}`}</Heading>
        <div className="vh-75">
          <Card className="h-100 overflow-hidden">
            <Table showMenu={v} data={data} schema={schema} />
          </Card>
        </div>
      </Column>
    ))}
  </Row>
    </div>
  );
};

```


#### Toggle Option For Header Row

```jsx
import { Row, Column, Heading, Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Carin",
        "lastName": "Robiou",
        "email": "crobioua@skype.com",
        "gender": "Female",
        "status": "Completed"
    },
    {
        "firstName": "Anson",
        "lastName": "Gamon",
        "email": "agamonb@economist.com",
        "gender": "Male"
    },
    {
        "firstName": "Brina",
        "lastName": "Pirie",
        "email": "bpiriec@stumbleupon.com",
        "gender": "Female"
    },
    {
        "firstName": "Hermy",
        "lastName": "Dyett",
        "email": "hdyettd@boston.com",
        "gender": "Male"
    },
    {
        "firstName": "Aime",
        "lastName": "von Hagt",
        "email": "avonhagte@nyu.edu",
        "gender": "Female"
    },
    {
        "firstName": "Gusti",
        "lastName": "Haycock",
        "email": "ghaycockf@virginia.edu",
        "gender": "Female"
    },
    {
        "firstName": "Mortimer",
        "lastName": "Kunneke",
        "email": "mkunnekeg@weather.com",
        "gender": "Male"
    },
    {
        "firstName": "Barnie",
        "lastName": "Pohls",
        "email": "bpohlsh@columbia.edu",
        "gender": "Male"
    },
    {
        "firstName": "Elliot",
        "lastName": "Nealey",
        "email": "enealeyi@cocolog-nifty.com",
        "gender": "Male"
    },
    {
        "firstName": "Allsun",
        "lastName": "Gong",
        "email": "agongj@discuz.net",
        "gender": "Female"
    },
    {
        "firstName": "Harwell",
        "lastName": "Kegan",
        "email": "hkegank@domainmarket.com",
        "gender": "Male"
    },
    {
        "firstName": "Gilles",
        "lastName": "Sandell",
        "email": "gsandelll@apache.org",
        "gender": "Male"
    },
    {
        "firstName": "Hilliard",
        "lastName": "Beamish",
        "email": "hbeamishm@shop-pro.jp",
        "gender": "Male"
    },
    {
        "firstName": "Charley",
        "lastName": "Kuschek",
        "email": "ckuschekn@dropbox.com",
        "gender": "Male"
    },
    {
        "firstName": "Danny",
        "lastName": "Churchin",
        "email": "dchurchino@bbc.co.uk",
        "gender": "Female"
    },
    {
        "firstName": "Ervin",
        "lastName": "Chatelain",
        "email": "echatelainp@mac.com",
        "gender": "Male"
    },
    {
        "firstName": "Milli",
        "lastName": "Joseph",
        "email": "mjosephq@merriam-webster.com",
        "gender": "Female"
    },
    {
        "firstName": "Greer",
        "lastName": "O'Doherty",
        "email": "godohertyr@homestead.com",
        "gender": "Female"
    },
    {
        "firstName": "Haroun",
        "lastName": "Martensen",
        "email": "hmartensens@skype.com",
        "gender": "Male"
    },
    {
        "firstName": "Desiree",
        "lastName": "Colwell",
        "email": "dcolwellt@businessinsider.com",
        "gender": "Female"
    },
    {
        "firstName": "Almeda",
        "lastName": "Jowsey",
        "email": "ajowseyu@ask.com",
        "gender": "Female"
    },
    {
        "firstName": "Cinderella",
        "lastName": "Dunnet",
        "email": "cdunnetv@mac.com",
        "gender": "Female"
    },
    {
        "firstName": "Hubert",
        "lastName": "Legion",
        "email": "hlegionw@ameblo.jp",
        "gender": "Male"
    },
    {
        "firstName": "Costa",
        "lastName": "Adamovsky",
        "email": "cadamovskyx@joomla.org",
        "gender": "Male"
    },
    {
        "firstName": "Kristan",
        "lastName": "Bielfeld",
        "email": "kbielfeldy@live.com",
        "gender": "Female"
    },
    {
        "firstName": "Sammy",
        "lastName": "Shermore",
        "email": "sshermorez@washington.edu",
        "gender": "Female"
    },
    {
        "firstName": "Kathi",
        "lastName": "Dowyer",
        "email": "kdowyer10@bluehost.com",
        "gender": "Female"
    },
    {
        "firstName": "Kennith",
        "lastName": "Whitehouse",
        "email": "kwhitehouse11@cornell.edu",
        "gender": "Male"
    },
    {
        "firstName": "Brianna",
        "lastName": "Garland",
        "email": "bgarland12@wikipedia.org",
        "gender": "Female"
    },
    {
        "firstName": "Cristobal",
        "lastName": "Mapholm",
        "email": "cmapholm13@constantcontact.com",
        "gender": "Male"
    },
    {
        "firstName": "Zia",
        "lastName": "Harrowing",
        "email": "zharrowing14@huffingtonpost.com",
        "gender": "Female"
    },
    {
        "firstName": "Zabrina",
        "lastName": "Gravener",
        "email": "zgravener15@ameblo.jp",
        "gender": "Female"
    },
    {
        "firstName": "Gregoor",
        "lastName": "Cruz",
        "email": "gcruz16@uol.com.br",
        "gender": "Male"
    },
    {
        "firstName": "Julita",
        "lastName": "Gemeau",
        "email": "jgemeau17@bandcamp.com",
        "gender": "Female"
    },
    {
        "firstName": "Gilbert",
        "lastName": "Sallier",
        "email": "gsallier18@dailymail.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Bride",
        "lastName": "Boniface",
        "email": "bboniface19@howstuffworks.com",
        "gender": "Female"
    },
    {
        "firstName": "Rodolph",
        "lastName": "Mattussevich",
        "email": "rmattussevich1a@nymag.com",
        "gender": "Male"
    },
    {
        "firstName": "Rowan",
        "lastName": "Rizon",
        "email": "rrizon1b@thetimes.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Avie",
        "lastName": "Nicolls",
        "email": "anicolls1c@nbcnews.com",
        "gender": "Female"
    },
    {
        "firstName": "Bram",
        "lastName": "Kleinhaut",
        "email": "bkleinhaut1d@imdb.com",
        "gender": "Male"
    },
    {
        "firstName": "Carmita",
        "lastName": "Costin",
        "email": "ccostin1e@hibu.com",
        "gender": "Female"
    },
    {
        "firstName": "Wash",
        "lastName": "Vannuchi",
        "email": "wvannuchi1f@japanpost.jp",
        "gender": "Male"
    },
    {
        "firstName": "Nikki",
        "lastName": "Faye",
        "email": "nfaye1g@feedburner.com",
        "gender": "Female"
    },
    {
        "firstName": "Aron",
        "lastName": "Scimonelli",
        "email": "ascimonelli1h@nationalgeographic.com",
        "gender": "Male"
    },
    {
        "firstName": "Smitty",
        "lastName": "Giacomello",
        "email": "sgiacomello1i@google.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Staci",
        "lastName": "D'Elias",
        "email": "sdelias1j@paginegialle.it",
        "gender": "Female"
    },
    {
        "firstName": "Radcliffe",
        "lastName": "Garbutt",
        "email": "rgarbutt1k@thetimes.co.uk",
        "gender": "Male"
    },
    {
        "firstName": "Maxwell",
        "lastName": "Krikorian",
        "email": "mkrikorian1l@ask.com",
        "gender": "Male"
    },
    {
        "firstName": "Dunstan",
        "lastName": "Chansonne",
        "email": "dchansonne1m@posterous.com",
        "gender": "Male"
    },
    {
        "firstName": "Isaak",
        "lastName": "Faherty",
        "email": "ifaherty1n@who.int",
        "gender": "Male"
    },
    {
        "firstName": "Sawyere",
        "lastName": "Ede",
        "email": "sede1o@drupal.org",
        "gender": "Male"
    },
    {
        "firstName": "Perren",
        "lastName": "Daddow",
        "email": "pdaddow1p@indiegogo.com",
        "gender": "Male"
    },
    {
        "firstName": "Brendis",
        "lastName": "Napier",
        "email": "bnapier1q@multiply.com",
        "gender": "Male"
    },
    {
        "firstName": "Francene",
        "lastName": "Godbold",
        "email": "fgodbold1r@joomla.org",
        "gender": "Female"
    },
    {
        "firstName": "Moll",
        "lastName": "Fludgate",
        "email": "mfludgate1s@who.int",
        "gender": "Female"
    },
    {
        "firstName": "Allayne",
        "lastName": "Medhurst",
        "email": "amedhurst1t@is.gd",
        "gender": "Male"
    },
    {
        "firstName": "Genvieve",
        "lastName": "Mellows",
        "email": "gmellows1u@stumbleupon.com",
        "gender": "Female"
    },
    {
        "firstName": "Rebe",
        "lastName": "Durnford",
        "email": "rdurnford1v@biglobe.ne.jp",
        "gender": "Female"
    },
    {
        "firstName": "Thalia",
        "lastName": "Joerning",
        "email": "tjoerning1w@netscape.com",
        "gender": "Female"
    },
    {
        "firstName": "Beckie",
        "lastName": "Lammin",
        "email": "blammin1x@gnu.org",
        "gender": "Female"
    },
    {
        "firstName": "Kassandra",
        "lastName": "Furney",
        "email": "kfurney1y@surveymonkey.com",
        "gender": "Female"
    },
    {
        "firstName": "Libbie",
        "lastName": "Gladyer",
        "email": "lgladyer1z@dropbox.com",
        "gender": "Female"
    },
    {
        "firstName": "Kai",
        "lastName": "Goldsbury",
        "email": "kgoldsbury20@census.gov",
        "gender": "Female"
    },
    {
        "firstName": "Arielle",
        "lastName": "De Bell",
        "email": "adebell21@addthis.com",
        "gender": "Female"
    },
    {
        "firstName": "Ellary",
        "lastName": "Warnock",
        "email": "ewarnock22@ted.com",
        "gender": "Male"
    },
    {
        "firstName": "Skelly",
        "lastName": "Blakes",
        "email": "sblakes23@reddit.com",
        "gender": "Male"
    },
    {
        "firstName": "Roanne",
        "lastName": "Stanyforth",
        "email": "rstanyforth24@com.com",
        "gender": "Female"
    },
    {
        "firstName": "Cash",
        "lastName": "Fettis",
        "email": "cfettis25@go.com",
        "gender": "Male"
    },
    {
        "firstName": "Farleigh",
        "lastName": "McDavid",
        "email": "fmcdavid26@sbwire.com",
        "gender": "Male"
    },
    {
        "firstName": "Holly",
        "lastName": "Barfford",
        "email": "hbarfford27@wsj.com",
        "gender": "Female"
    },
    {
        "firstName": "Hurley",
        "lastName": "Benaine",
        "email": "hbenaine28@sun.com",
        "gender": "Male"
    },
    {
        "firstName": "Maryjo",
        "lastName": "Gilhooly",
        "email": "mgilhooly29@tripod.com",
        "gender": "Female"
    },
    {
        "firstName": "Annis",
        "lastName": "Linkie",
        "email": "alinkie2a@wp.com",
        "gender": "Female"
    },
    {
        "firstName": "Mariel",
        "lastName": "Husher",
        "email": "mhusher2b@etsy.com",
        "gender": "Female"
    },
    {
        "firstName": "Niels",
        "lastName": "Klimontovich",
        "email": "nklimontovich2c@surveymonkey.com",
        "gender": "Male"
    },
    {
        "firstName": "Udall",
        "lastName": "Linfitt",
        "email": "ulinfitt2d@toplist.cz",
        "gender": "Male"
    },
    {
        "firstName": "Isidore",
        "lastName": "Kuhn",
        "email": "ikuhn2e@cdc.gov",
        "gender": "Male"
    },
    {
        "firstName": "Rosemonde",
        "lastName": "Kettle",
        "email": "rkettle2f@techcrunch.com",
        "gender": "Female"
    },
    {
        "firstName": "Cass",
        "lastName": "Boot",
        "email": "cboot2g@furl.net",
        "gender": "Male"
    },
    {
        "firstName": "Montague",
        "lastName": "Rossey",
        "email": "mrossey2h@goo.gl",
        "gender": "Male"
    },
    {
        "firstName": "Geno",
        "lastName": "Jenkyn",
        "email": "gjenkyn2i@opensource.org",
        "gender": "Male"
    },
    {
        "firstName": "Esdras",
        "lastName": "Skivington",
        "email": "eskivington2j@answers.com",
        "gender": "Male"
    },
    {
        "firstName": "Gabriello",
        "lastName": "Luce",
        "email": "gluce2k@nydailynews.com",
        "gender": "Male"
    },
    {
        "firstName": "Magdalene",
        "lastName": "Ilyunin",
        "email": "milyunin2l@prweb.com",
        "gender": "Female"
    },
    {
        "firstName": "Isidro",
        "lastName": "Fawson",
        "email": "ifawson2m@squidoo.com",
        "gender": "Male"
    },
    {
        "firstName": "Blinny",
        "lastName": "Palfrey",
        "email": "bpalfrey2n@networksolutions.com",
        "gender": "Female"
    },
    {
        "firstName": "Justen",
        "lastName": "Kordas",
        "email": "jkordas2o@symantec.com",
        "gender": "Male"
    },
    {
        "firstName": "Damien",
        "lastName": "Hallede",
        "email": "dhallede2p@unicef.org",
        "gender": "Male"
    },
    {
        "firstName": "Jaquelyn",
        "lastName": "Rockhall",
        "email": "jrockhall2q@vkontakte.ru",
        "gender": "Female"
    },
    {
        "firstName": "Garrek",
        "lastName": "Matignon",
        "email": "gmatignon2r@noaa.gov",
        "gender": "Male"
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: 300,
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      sorting: false,
      translate: _ => ({
        icon: 'events'
      })
    },
  ];

  const values = [true, false];

  return (
    <div className="d-flex flex-wrap">
    <Row>
    {values.map((v, index) => (
      <Column key={index} size={5} className="ml-10">
        <Heading>{`showHead: ${v}`}</Heading>
        <div className="vh-75">
          <Card className="h-100 overflow-hidden">
            <Table showHead={v} data={data} schema={schema} />
          </Card>
        </div>
      </Column>
    ))}
  </Row>
    </div>
  );
};

```


#### Data table

```jsx
import { Card, Table } from '@innovaccer/design-system';

() => {
  const data = [
    {
      claim_id: 'Q10000101',
      claim_type: 'Professional',
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "03/27/2020",
      last_dos: "03/30/2020",
      firstName: 'Brooke',
      lastName: 'Heeran',
    },
    {
      claim_id: 'Q10000102',
      claim_type: "Professional",
      plan_name: "MSSP Track 1",
      insurance_name: "Medicare",
      first_dos: "03/24/2020",
      last_dos: "04/30/2020",
      firstName: 'Frazer',
      lastName: 'Cathro',
    },
    {
      claim_id: 'Q10000103',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "05/16/2020",
      last_dos: "05/30/2020",
      firstName: 'Lemmie',
      lastName: 'Ciric',
    },
    {
      claim_id: 'Q10000104',
      claim_type: "Institutional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "12/27/2020",
      last_dos: "12/30/2020",
      firstName: 'Randy',
      lastName: 'Boatwright',
    },
    {
      claim_id: 'Q10000105',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "05/04/2020",
      last_dos: "05/28/2020",
      firstName: 'Rolando',
      lastName: 'Cyples',
    },
    {
      claim_id: 'Q10000106',
      claim_type: "Institutional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "01/27/2020",
      last_dos: "03/30/2020",
      firstName: 'Lem',
      lastName: 'Males',
    },
    {
      claim_id: 'Q10000107',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "03/30/2020",
      last_dos: "04/30/2020",
      firstName: 'Sayres',
      lastName: 'Adelberg',
    },
    {
      claim_id: 'Q10000108',
      claim_type: "Professional",
      plan_name: "MSSP Track 3",
      insurance_name: "Medicare",
      first_dos: "02/27/2020",
      last_dos: "03/30/2020",
      firstName: 'Murray',
      lastName: 'Bravington',
    },
    {
      claim_id: 'Q10000109',
      claim_type: "Institutional",
      plan_name: "MSSP Track 5",
      insurance_name: "Medicare",
      first_dos: "03/17/2020",
      last_dos: "03/30/2020",
      firstName: 'Carin',
      lastName: 'Robiou',
    },
    {
      claim_id: 'Q100001010',
      claim_type: "Institutional",
      plan_name: "MSSP Track 6",
      insurance_name: "Medicare",
      first_dos: "09/27/2020",
      last_dos: "12/27/2020",
      firstName: 'Brina',
      lastName: 'Pirie',
    }
  ];

  const schema = [
    {
      name: 'claim_id',
      displayName: 'Claim Id',
      width: '12%',
      separator: true,
    },
    {
      name: 'claim_type',
      displayName: 'Claim Type',
      width: '15%',
      separator: true,
      cellType: "DEFAULT"
    },
    {
      name: 'insurance_name',
      displayName: 'Insurance Name',
      width: '15%',
      separator: true,
    },
    {
      name: 'plan_name',
      displayName: 'Plan Name',
      width: '15%',
      separator: true,
    },
    {
      name: 'first_dos',
      displayName: 'First Date of Service',
      width: '18%',
      separator: true,
    },
    {
      name: 'last_dos',
      displayName: 'Last Date of Service',
      width: '18%',
      separator: true,
    },
    {
      name: 'provider_name',
      displayName: 'Provider Name',
      separator: true,
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      translate: (a) => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
    },
  ];

  const loaderSchema = [
    {
        "name": "name",
        "displayName": "Name",
        "width": "40%",
        "resizable": true,
        "tooltip": true,
        "separator": true,
        "filters": [
            {
                "label": "A-G",
                "value": "a-g"
            },
            {
                "label": "H-R",
                "value": "h-r"
            },
            {
                "label": "S-Z",
                "value": "s-z"
            }
        ],
        "cellType": "AVATAR_WITH_TEXT"
    },
    {
        "name": "email",
        "displayName": "Email",
        "width": 250,
        "resizable": true,
        "sorting": false,
        "cellType": "WITH_META_LIST"
    },
    {
        "name": "gender",
        "displayName": "Gender",
        "width": 180,
        "resizable": true,
        "cellType": "STATUS_HINT",
        "filters": [
            {
                "label": "Male",
                "value": "male"
            },
            {
                "label": "Female",
                "value": "female"
            }
        ]
    },
    {
        "name": "icon",
        "displayName": "Icon",
        "width": 100,
        "resizable": true,
        "align": "center",
        "cellType": "ICON"
    },
    {
        "name": "customCell",
        "displayName": "Custom Cell",
        "width": 200,
        "resizable": true,
        "cellType": "WITH_META_LIST"
    }
];

  return (
      <Card className="overflow-hidden">
        <Table
          loaderSchema={loaderSchema}
          showMenu={false}
          separator={true}
          data={data}
          schema={schema}
          withHeader={true}
          headerOptions={{
            withSearch: true
          }}
          onSearch={(currData, searchTerm) => {
            return currData.filter(d =>
              d.firstName.toLowerCase().match(searchTerm.toLowerCase())
              || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
              || d.claim_id.toLowerCase().match(searchTerm.toLowerCase())
            );
          }}
          withPagination={true}
          pageSize={5}
          onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
        />
      </Card>
  );
}
```


#### Resource Table

```jsx
import { Avatar, Menu, Text, Card, Table } from '@innovaccer/design-system';


() => {
  const data = [
    {
        "name": "Asthma Outreach",
        "firstName": "Brooke",
        "lastName": "Heeran",
        "status": "In Progress",
        "lastUpdated": "June 20, 2020",
        "recipients": 11846
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "status": "Scheduled",
        "lastUpdated": "June 19, 2020",
        "name": "HbA1c Test due",
        "recipients": 12846
    },
    {
        "firstName": "Lemmie",
        "name": "ER Education",
        "lastName": "Ciric",
        "status": "Draft",
        "lastUpdated": "May 19, 2020",
        "recipients": 118467
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "name": "Flu Vaccination",
        "status": "Failed",
        "lastUpdated": "March 19, 2020",
        "recipients": 10846
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "name": "Well-child Visit",
        "status": "In Progress",
        "lastUpdated": "April 19, 2020",
        "recipients": 11847
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "name": "Annual wellness Visit",
        "status": "In Progress",
        "lastUpdated": "June 16, 2020",
        "recipients": 118100
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "name": "Flu Vaccination",
        "status": "Draft",
        "lastUpdated": "Dec 19, 2020",
        "recipients": 11848
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "name": "Well-child Visit",
        "status": "Draft",
        "lastUpdated": "April 19, 2020",
        "recipients": 11890
    }
];

  const statusAppearance = {
    'In Progress': 'info',
    'Scheduled': 'warning',
    'Draft': 'default',
    'Failed': 'alert'
  };

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '30%',
      cellType: 'WITH_META_LIST',
      sorting: false,
      translate: a => ({
        title: a.name,
        metaList: [`${a.recipients} recipients`]
      }),
    },
    {
      name: 'status',
      displayName: 'Status',
      width: '20%',
      cellType: 'STATUS_HINT',
      sorting: false,
      filters: [
        { label: 'In Progress', value: 'In Progress' },
        { label: 'Scheduled', value: 'Scheduled' },
        { label: 'Draft', value: 'Draft' },
        { label: 'Failed', value: 'Failed' }
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.status === filter) return true;
        }
        return false;
      },
      translate: a => {
        const status = a.status;
        return ({
          title: status,
          statusAppearance: statusAppearance[status]
        });
      }
    },
    {
      name: 'lastUpdated',
      displayName: 'Last Updated on',
      width: '30%',
      sorting: false,
    },
    {
      name: 'user',
      displayName: '',
      sorting: false,
      width: '20%',
      cellRenderer: (props) => {
        const { data } = props;
        return (
          <div className="d-flex align-items-center justify-content-end flex-grow-1">
            <Avatar firstName={data.firstName} lastName={data.lastName} />
            <div className="ml-6">
              <Menu trigger={<Menu.Trigger appearance="transparent" />}>
                <Menu.List>
                  <Menu.Item>
                    <Text>Edit</Text>
                  </Menu.Item>
                  <Menu.Item>
                    <Text>Delete</Text>
                  </Menu.Item>
                </Menu.List>
              </Menu>
            </div>
          </div>
        );
      }
    }
  ];

  return (
    <Card className="overflow-hidden">
      <Table
        showMenu={false}
        type="resource"
        data={data}
        schema={schema}
        withHeader={true}
        filterPosition="HEADER"
        onSelect={(rowIndex, selected, selectedList, selectAll) =>
          console.log(`on-select:- rowIndex: ${rowIndex} selected: ${selected} selectedList: ${JSON.stringify(selectedList)} selectAll: ${selectAll}`)
        }
        headerOptions={{
          withSearch: true
        }}
        filterList={{
          status: ['In Progress', 'Scheduled', 'Draft', 'Failed']
        }}
        onSearch={(currData, searchTerm) => {
          return currData.filter(d =>
            d.firstName.toLowerCase().match(searchTerm.toLowerCase())
            || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
            || d.name.toLowerCase().match(searchTerm.toLowerCase())
          );
        }}
        withPagination={true}
        paginationType="basic"
        pageSize={4}
        onPageChange={newPage => console.log(`on-page-change:- ${newPage}`)}
      />
    </Card>
  );
};

```# Tabs

Tabs segregate similar kind of content and allow users to navigate between them without switching the context.

### Code Examples

#### Components Tabs All

```jsx
import { Tabs, Tab } from '@innovaccer/design-system';

() => {
  const [activeIndex, setActiveIndex] = React.useState(0);

  const onTabChangeHandler = (tabIndex) => {
    setActiveIndex(tabIndex);
  };

  return(
    <Tabs activeIndex={activeIndex} onTabChange={onTabChangeHandler} className="mb-6" headerClassName="pl-3">
      <Tab label="All" count={15} className="pl-6">
        <div>All</div>
      </Tab>
      <Tab label="Pending" count={5} className="pl-6">
        <div>Pending</div>
      </Tab>
      <Tab label="Transferred" count={3} className="pl-6">
        <div>Transferred</div>
      </Tab>
      <Tab label="Successful" count={2} className="pl-6">
        <div>Successful</div>
      </Tab>
      <Tab label="Declined" disabled={true} count={5}>
        <div>Declined</div>
      </Tab>
    </Tabs>
  );
}
```


#### Components Tabs Basic Tabs

```jsx
import { Heading, Select, Tabs, Tab } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Feb 9, 2019 (recent)',
      value: 'Feb 9, 2019 (recent)',
      selected: true
    },
    {
      label: 'Feb 10, 2019',
      value: 'Feb 10, 2019'
    },
    {
      label: 'Feb 11, 2019',
      value: 'Feb 11, 2019'
    },
    {
      label: 'Feb 12, 2019',
      value: 'Feb 12, 2019'
    },
    {
      label: 'Feb 13, 2019',
      value: 'Feb 13, 2019'
    }
  ];

  const [activeIndex, setActiveIndex] = React.useState(0);

  const onTabChangeHandler = (tabIndex) => {
    setActiveIndex(tabIndex);
  };

  return(
    <div>
      <div className="d-flex justify-content-between">
        <Heading size="m" className="pl-5">
          Data Gaps
        </Heading>
        <div style={{ width: 'var(--spacing-8)' }}>
          <Select
            value={{ label: options[0].label, value: options[0].value }}
            triggerOptions={{ withClearButton: false }}
          >
            <Select.List>
              {options.map((item, key) => {
                return (
                  <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                    {item.label}
                  </Select.Option>
                )
              })}
            </Select.List>
          </Select>
        </div>
      </div>
      <Tabs activeIndex={activeIndex} onTabChange={onTabChangeHandler} className="mb-6">
        <Tab label="Clinical Gaps" className="pl-5">
          <div>Clinical Gaps</div>
        </Tab>
        <Tab label="Billing Gaps" className="pl-5">
          <div>Billing Gaps</div>
        </Tab>
        <Tab label="Claim Gaps" disabled={true}>
          <div>Claim Gaps</div>
        </Tab>
      </Tabs>
    </div>
  );
}
```


#### Components Tabs Custom Labels

```jsx
import { Tabs, Tab, Pills, Text } from '@innovaccer/design-system';

() => {
  const [activeIndex, setActiveIndex] = React.useState(0);

  const onTabChangeHandler = (tabIndex) => {
    setActiveIndex(tabIndex);
    console.log(`tab-change: ${tabIndex}`)();
  };

  return (
    <Tabs activeIndex={activeIndex} onTabChange={onTabChangeHandler} className="mb-6">
      <Tab
        className="pl-5"
        label={
          <>
            <div className="d-flex mr-4">
              <Pills appearance={activeIndex === 0 ? 'primary' : 'secondary'}>10</Pills>
            </div>
            <Text appearance={activeIndex !== 0 ? 'subtle' : 'link'}>Custom Label 1</Text>
          </>
        }
      >
        <div>Custom Label 1</div>
      </Tab>
      <Tab
        className="pl-5"
        label={
          <>
            <div className="d-flex mr-4">
              <Pills appearance={activeIndex === 1 ? 'primary' : 'secondary'}>5</Pills>
            </div>
            <Text appearance={activeIndex !== 1 ? 'subtle' : 'link'}>Custom Label 2</Text>
          </>
        }
      >
        <div>Custom Label 2</div>
      </Tab>
      <Tab
        label={
          <>
            <div className="d-flex mr-4">
              <Pills appearance={activeIndex === 2 ? 'primary' : 'secondary'}>5</Pills>
            </div>
            <Text appearance={activeIndex !== 2 ? 'subtle' : 'link'}>Custom Label 3</Text>
          </>
        }
        disabled={true}
      >
        <div>Custom Label 3</div>
      </Tab>
    </Tabs>
  );
}
```


#### Components Tabs Disabled With Activated

```jsx
import { Tabs, Tab, EmptyState } from '@innovaccer/design-system';

() => {
  const [activeIndex, setActiveIndex] = React.useState(0);

  const onTabChangeHandler = (tabIndex) => {
    setActiveIndex(tabIndex);
  };

  const isDisabled = true;
  return (
    <Tabs activeIndex={activeIndex} onTabChange={onTabChangeHandler} className="mb-6">
      <Tab label="All" icon="call_received" disabled={isDisabled}>
        {isDisabled ? (
          <div className="h-100 pb-5 bg-secondary-lightest">
            <EmptyState
              title="There's a problem loading this page."
              description="Tab is disabled and you are not authorized to see the content of this tab"
              size="large"
            ></EmptyState>
          </div>
        ) : (
          <div>All</div>
        )}
      </Tab>
      <Tab label="Successful" icon="check_circle">
        <div>Successful</div>
      </Tab>
      <Tab label="Declined" disabled={true} icon="warning">
        <div>Declined</div>
      </Tab>
    </Tabs>
  );
}
```


#### Components Tabs Dismissible Tab

```jsx
import { Tabs, Tab } from '@innovaccer/design-system';

() => {
  
  const [activeIndex, setActiveIndex] = React.useState(0);
  const [dismissList, setDismissList] = React.useState([]);

  const onTabChangeHandler = (tabIndex) => {
    setActiveIndex(tabIndex);
  };

  const onDismissHandler = (tabInfo) => {
    let newList = [...dismissList];
    newList.push(tabInfo.label);
    setDismissList(newList);
  };

  return (
    <Tabs activeIndex={activeIndex} onTabChange={onTabChangeHandler} className="mb-6">
      {!dismissList.includes('All') && (
        <Tab label="All" count={15} className="pl-5">
          <div>All</div>
        </Tab>
      )}
      {!dismissList.includes('Pending') && (
        <Tab
          label="Pending"
          className="pl-5"
          count={10}
          isDismissible={true}
          onDismiss={(tabInfo) => onDismissHandler(tabInfo)}
        >
          <div>Pending</div>
        </Tab>
      )}
      {!dismissList.includes('Declined') && (
        <Tab
          label="Declined"
          className="pl-5"
          count={4}
          isDismissible={true}
          onDismiss={(tabInfo) => onDismissHandler(tabInfo)}
        >
          <div>Declined</div>
        </Tab>
      )}
      <Tab label="Successful" disabled={true} count={1} isDismissible={true}>
        <div>Successful</div>
      </Tab>
    </Tabs>
  );
}
```


#### Components Tabs Inline Content

```jsx
import { Tabs, Tab, Input, Select } from '@innovaccer/design-system';

() => {
  const [activeIndex, setActiveIndex] = React.useState(0);

  const options = [
    {
      label: 'Increasing',
      value: 'Increasing',
    },
    {
      label: 'Decreasing',
      value: 'Decreasing'
    },
  ];

  const onTabChangeHandler = (tabIndex) => {
    setActiveIndex(tabIndex);
  };

  return(
    <Tabs
      onTabChange={onTabChangeHandler}
      className="mb-6"
      activeIndex={activeIndex}
    >
      <Tab label="All" count={12} className="pl-5">
        <div>All</div>
      </Tab>
      <Tab label="Active User" count={3} className="pl-5">
        <div>Active User</div>
      </Tab>
      <Tab label="Inactive User" count={9} className="pl-5">
        <div>Inactive User</div>
      </Tab>
      <div className="d-flex justify-content-end flex-grow-1">
        <div style={{ width: 'var(--spacing-9)' }} className="ml-8">
          <Input placeholder="Search by name" icon="search" />
        </div>
        <div style={{ width: 'var(--spacing-8)' }} className="ml-4">
          <Select
            triggerOptions={{ 
              withClearButton: false,
              placeholder: 'Sort by',
            }}
          >
            <Select.List>
              {options.map((item, key) => {
                return (
                  <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                    {item.label}
                  </Select.Option>
                )
              })}
            </Select.List>
          </Select>
        </div>
      </div>
    </Tabs>
  );
}
```


#### Components Tabs Size

```jsx
import { Text, Tabs, Tab } from '@innovaccer/design-system';


  () => {
    const [activeIndex, setActiveIndex] = React.useState(0);

    const onTabChangeHandler = (tabIndex) => {
      setActiveIndex(tabIndex);
    };

    return (
      <div className="d-flex w-100">
        <div className="d-flex flex-column">
          <Text weight="strong" className="mb-5">
            Regular
          </Text>
          <Tabs activeIndex={activeIndex} onTabChange={onTabChangeHandler} className="mb-6 mr-10" headerClassName="pl-3">
            <Tab label="All" count={15} className="pl-6">
              <div>All</div>
            </Tab>
            <Tab label="Successful" count={5} className="pl-6">
              <div>Successful</div>
            </Tab>
            <Tab label="Declined" count={10} className="pl-6">
              <div>Declined</div>
            </Tab>
          </Tabs>
        </div>

        <div className="d-flex flex-column">
          <Text weight="strong" className="mb-5">
            Small
          </Text>
          <Tabs
            size="small"
            activeIndex={activeIndex}
            onTabChange={onTabChangeHandler}
            className="mb-6"
            headerClassName="pl-3"
          >
            <Tab label="All" count={15} className="pl-6">
              <div>All</div>
            </Tab>
            <Tab label="Successful" count={5} className="pl-6">
              <div>Successful</div>
            </Tab>
            <Tab label="Declined" count={10} className="pl-6">
              <div>Declined</div>
            </Tab>
          </Tabs>
        </div>
      </div>
    );
  }

```


#### Components Tabs Tab Label Overflow

```jsx
import { Tabs, Tab } from '@innovaccer/design-system';

() => {
  const [activeIndex, setActiveIndex] = React.useState(0);

  const onTabChangeHandler = (tabIndex) => {
    setActiveIndex(tabIndex);
  };

  return(
    <Tabs activeIndex={activeIndex} onTabChange={onTabChangeHandler} className="mb-6" headerClassName="pl-3">
      <Tab label="All" count={15} className="pl-6">
        <div>All</div>
      </Tab>
      <Tab label="Pending" count={5} className="pl-6">
        <div>Pending</div>
      </Tab>
      <Tab label="A very very very very very long tab label" count={3} className="pl-6">
        <div>A very very very very very long tab label</div>
      </Tab>
      <Tab label="Successful" count={2} className="pl-6">
        <div>Successful</div>
      </Tab>
      <Tab label="Declined" disabled={true} count={5}>
        <div>Declined</div>
      </Tab>
    </Tabs>
  );
}
```


#### Components Tabs Tabs With Count

```jsx
import { Heading, Button, Tabs, Tab, Input, Select } from '@innovaccer/design-system';

() => {
  const options = [
    {
      label: 'Increasing',
      value: 'Increasing',
    },
    {
      label: 'Decreasing',
      value: 'Decreasing'
    },
  ];

  const [activeIndex, setActiveIndex] = React.useState(0);

  const onTabChangeHandler = (tabIndex) => {
    setActiveIndex(tabIndex);
  };

  return(
    <div>
      <div className="d-flex justify-content-between">
        <Heading size="m" className="pl-5">Strategy</Heading>
        <Button appearance="primary">New Strategy</Button>
      </div>
      <div className="d-flex align-items-center mt-3" >
        <Tabs
          onTabChange={onTabChangeHandler}
          className="mb-6"
          activeIndex={activeIndex}
        >
          <Tab label="All" count={12} className="pl-5">
            <div>All</div>
          </Tab>
          <Tab label="Active User" count={3} className="pl-5">
            <div>Active User</div>
          </Tab>
          <Tab label="Inactive User" count={9} className="pl-5">
            <div>Inactive User</div>
          </Tab>
          <div className="d-flex align-items-center">
            <div style={{ width: 'var(--spacing-9)' }} className="ml-8">
              <Input placeholder="Search by name" icon="search" />
            </div>
            <div style={{ width: 'var(--spacing-8)' }} className="ml-4">
              <Select
                triggerOptions={{ 
                  withClearButton: false,
                  placeholder: 'Sort by',
                }}
              >
                <Select.List>
                  {options.map((item, key) => {
                    return (
                      <Select.Option key={key} option={{ label: item.label, value: item.value }}>
                        {item.label}
                      </Select.Option>
                    )
                  })}
                </Select.List>
              </Select>
            </div>
          </div>
        </Tabs>
      </div>
    </div>
  );
}
```


#### Components Tabs Tabs With Icon

```jsx
import { Heading, Link, Tabs, Tab } from '@innovaccer/design-system';

() => {
  const [activeIndex, setActiveIndex] = React.useState(0);

  const onTabChangeHandler = (tabIndex) => {
    setActiveIndex(tabIndex);
  };

  return(
    <div>
      <div className="d-flex align-items-center">
        <Heading size="s" className="pl-5">Diabetes: Hemoglobin A1c Poor Control</Heading>
        <Link className="ml-4">Measure definition</Link>
      </div>
      <Tabs
        activeIndex={activeIndex}
        onTabChange={onTabChangeHandler}
        className="mb-6"
      >
        <Tab label="2020" icon="warning" className="pl-5">
          <div>2020</div>
        </Tab>
        <Tab label="2019" icon="check_circle" className="pl-5">
          <div>2019</div>
        </Tab>
        <Tab label="2018" icon="warning" className="pl-5">
          <div>2018</div>
        </Tab>
        <Tab label="2017" icon="check_circle" className="pl-5">
          <div>2017</div>
        </Tab>
      </Tabs>
    </div>
  );
}
```# Text



### Code Examples

#### Text

```jsx
import { Text } from '@innovaccer/design-system';

() => {
  return <Text>Text component have different variants, look for options in knobs tab.</Text>;
}
```


#### Text

```jsx
import { Text } from '@innovaccer/design-system';

() => {
  const appearances = ['default', 'white', 'destructive', 'subtle', 'disabled', 'success', 'link'];
  return (
    <div className="d-flex w-75 justify-content-between">
      {appearances.map((appear, ind) => {
        const backgroundClass = appear === 'white' ? 'bg-dark mr-6' : '';

        return (
          <Text key={ind} className={backgroundClass} appearance={appear}>
            {appear.charAt(0).toUpperCase() + appear.slice(1)}
          </Text>
        );
      })}
    </div>
  );
}
```


#### Text

```jsx
import { Row, Column, Text } from '@innovaccer/design-system';

() => {
  const colorList = [
    [
      'primary',
      'primary-dark',
      'primary-darker',
      'primary-light',
      'primary-lighter',
      'primary-lightest',
      'primary-shadow',
    ],
    [
      'success',
      'success-dark',
      'success-darker',
      'success-light',
      'success-lighter',
      'success-lightest',
      'success-shadow',
    ],
    ['alert', 'alert-dark', 'alert-darker', 'alert-light', 'alert-lighter', 'alert-lightest', 'alert-shadow'],
    [
      'warning',
      'warning-dark',
      'warning-darker',
      'warning-light',
      'warning-lighter',
      'warning-lightest',
      'warning-shadow',
    ],
    [
      'accent1',
      'accent1-dark',
      'accent1-darker',
      'accent1-light',
      'accent1-lighter',
      'accent1-lightest',
      'accent1-shadow',
    ],
    [
      'accent2',
      'accent2-dark',
      'accent2-darker',
      'accent2-light',
      'accent2-lighter',
      'accent2-lightest',
      'accent2-shadow',
    ],
    [
      'accent3',
      'accent3-dark',
      'accent3-darker',
      'accent3-light',
      'accent3-lighter',
      'accent3-lightest',
      'accent3-shadow',
    ],
    [
      'accent4',
      'accent4-dark',
      'accent4-darker',
      'accent4-light',
      'accent4-lighter',
      'accent4-lightest',
      'accent4-shadow',
    ],
    ['secondary', 'secondary-dark', 'secondary-light', 'secondary-lighter', 'secondary-lightest', 'secondary-shadow'],

    ['white', 'inverse', 'inverse-light', 'inverse-lighter', 'inverse-lightest', 'inverse-shadow'],
  ];

  return (
    <Row>
      {colorList.map((colors, key) => {
        return (
          <Row key={key} className="py-4">
            {colors.map((color, ind) => {
              return (
                <Column key={ind}>
                  <Text size="large" color={color} className={color === 'white' ? 'bg-dark' : ''}>
                    {color}
                  </Text>
                </Column>
              );
            })}
          </Row>
        );
      })}
    </Row>
  );
}
```


#### Text

```jsx
import { Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex align-items-center justify-content-between w-25">
      <Text size="small">Small</Text>
      <Text size="regular">Regular</Text>
      <Text size="large">Large</Text>
    </div>
  );
}
```


#### Text

```jsx
import { Text } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex justify-content-between w-25">
      <Text weight="strong">Strong</Text>
      <Text weight="medium">Medium</Text>
      <Text>Default</Text>
    </div>
  );
}
```# TextField



### Code Examples

#### TextField

```jsx
import { TextField } from '@innovaccer/design-system';

() => {
  const [inputText, setInputText] = React.useState('');
  const [helpText, setHelpText] = React.useState('');

  const maxLimit = 50

  React.useEffect(() => {
    if (inputText.length > maxLimit) {
      setHelpText('Character limit exceeded');
    } else {
      setHelpText('Pick a unique username');
    }
  }, [inputText]);

  return (
    <div className="w-25">
      <TextField
        max={maxLimit}
        value={inputText}
        onChange={(e) => {
          setInputText(e.target.value);
        }}
        label="Username"
        helpText={helpText}
      />
    </div>
  );
}
```


#### TextField

```jsx
import { TextField } from '@innovaccer/design-system';

() => {

  return (
    <div className="w-25">
      <TextField
        label="Username"
        helpText="Enter a unique name"
      />
    </div>
  );
}
```


#### TextField

```jsx
import { TextField } from '@innovaccer/design-system';

() => {
  const [inputText, setInputText] = React.useState('');
  const [helpText, setHelpText] = React.useState('');

  const maxLimit = 50

  React.useEffect(() => {
    if (inputText.length > maxLimit) {
      setHelpText('Character limit exceeded');
    } else {
      setHelpText('Enter billing details');
    }
  }, [inputText]);

  return (
    <div className="w-25">
      <TextField
        withTextarea={true}
        max={maxLimit}
        value={inputText}
        onChange={(e) => {
          setInputText(e.target.value); 
        }}
        label="Description"
        helpText={helpText}
      />
    </div>
  );
}
```


#### TextField

```jsx
import { TextField } from '@innovaccer/design-system';

() => {

  return (
    <div className="w-25">
      <TextField
        label="Description"
        withTextarea={true}
        helpText="Enter billing details"
      />
    </div>
  );
}
```# Textarea



### Code Examples

#### Components Input Textarea All

```jsx
import { Textarea } from '@innovaccer/design-system';

() => {
  const placeholder = 'Placeholder';

  const resize = true;

  const rows = 3;

  return (
    <div className="w-25">
      <Textarea
        name="Textarea"
        onChange={action('on-change')}
        onClick={action('on-click')}
        placeholder={placeholder}
        resize={resize}
        rows={rows}
        aria-labelledby="Textarea"
      />
    </div>
  );
}
```


#### Textarea

```jsx
import { Label, Textarea } from '@innovaccer/design-system';

() => (
  <div className="w-50">
    <Label withInput={true} htmlFor="comments">
      Comments
    </Label>
    <Textarea name="comments" id="comments" aria-labelledby="Comments" placeholder="Enter your comments here" />
  </div>
)
```


#### Textarea

```jsx
import { Label, Textarea, Caption } from '@innovaccer/design-system';

() => {
  const [value, setValue] = React.useState('Patient moved out of country last week.');

  return (
    <div className="w-50">
      <Label withInput={true} htmlFor="notes">
        Confirmation Notes
      </Label>
      <Textarea
        name="notes"
        value={value}
        onChange={(e) => {
          setValue(e.target.value);
        }}
        placeholder="Enter your comments here"
        aria-labelledby="Confirmation Notes"
        id="notes"
      />
      <Caption withInput={true}>This note will be automatically pinned for export.</Caption>
    </div>
  );
};
```


#### Textarea

```jsx
import { Label, Textarea } from '@innovaccer/design-system';

() => {
  return (
    <div className="d-flex">
      <div>
        <Label withInput={true}>Disabled</Label>
        <Textarea
          aria-labelledby="Textarea"
          disabled={true}
          resize={false}
          name="Textarea"
          placeholder="Placeholder"
          rows={3}
        />
      </div>
      <div className="ml-6">
        <Label withInput={true}>Enabled</Label>
        <Textarea
          aria-labelledby="Textarea"
          name="Textarea"
          placeholder="Placeholder"
          rows={3}
        />
      </div>
    </div>
  );
}
```


#### Textarea

```jsx
import { Label, Textarea } from '@innovaccer/design-system';

() => (
  <div className="w-50">
    <Label withInput={true} htmlFor="Error">
      Error
    </Label>
    <Textarea name="error" id="error" aria-labelledby="Error" error={true} placeholder="This is the error state." />
  </div>
)
```# TimePicker

Time picker is used for selecting or entering a time value.

### Code Examples

#### TimePicker

```jsx
import { TimePicker } from '@innovaccer/design-system';

() => {
  const onTimeChange = (val) => {
    console.log(val);
  };

  return (
    <div className="w-25">
      <TimePicker
        inputFormat={'hh:mm AM'}
        outputFormat={'hh:mm AM'}
        onTimeChange={onTimeChange}
      />
    </div>
  );
}
```


#### TimePicker

```jsx
import { TimePicker, HelpText } from '@innovaccer/design-system';

() => {
  const onTimeChange = (val) => {
    console.log(val);
  };

  return (
    <div className="w-25">
      <TimePicker
        inputFormat={'hh:mm AM'}
        outputFormat={'hh:mm AM'}
        onTimeChange={onTimeChange}
        error={true}
      />
      <HelpText error={true} message={'Error message goes here.'} />
    </div>
  );
}
```


#### TimePicker

```jsx
import { Row, Label, TimePicker } from '@innovaccer/design-system';

() => {

  return (
    <Row>
      <div className="w-25">
        <Label>12 Hour Format</Label>
        <TimePicker withSearch={true} disabledSlotList={['12:45 AM', '01:00 AM']} id="12-hour" />
      </div>

      <div className="w-25 ml-7">
        <Label>24 Hour Format</Label>
        <TimePicker timeFormat="24-Hour" withSearch={true} disabledSlotList={['00:45', '01:00']} id="24-hour" />
      </div>
    </Row>
  );
}
```


#### TimePicker

```jsx
import { Label, TimePicker } from '@innovaccer/design-system';

() => {

  const [startTime, setStartTime] = React.useState('00:00');

  const onFromChangeHandler = (props) => {
    setStartTime(props);
  };

  return (
    <div className="d-flex">
      <div className="w-25 mr-5">
        <Label withInput={true}>From</Label>
        <TimePicker withSearch={true} startTime="00:15 AM" endTime="11:45 PM" onChange={onFromChangeHandler} id="From" />
      </div>

      <div className="w-25">
        <Label withInput={true}>To</Label>
        <TimePicker withSearch={true} startTime={startTime} endTime="11:45 PM" showDuration={true} id="To" />
      </div>
    </div>
  );
}
```


#### TimePicker

```jsx
import { Row, Label, TimePicker } from '@innovaccer/design-system';

() => {

  return (
    <Row>
      <div className="w-25">
        <Label>12 Hour Format</Label>
        <TimePicker startTime="05:00" withSearch={true} showDuration={true} id="12-hour" />
      </div>

      <div className="w-25 ml-7">
        <Label>24 Hour Format</Label>
        <TimePicker startTime="05:00" timeFormat="24-Hour" withSearch={true} showDuration={true} id="24-hour" />
      </div>
    </Row>
  );
}
```


#### TimePicker

```jsx
import { Row, Label, TimePicker } from '@innovaccer/design-system';

() => {

  return (
    <Row>
      <div className="w-25">
        <Label>12 Hour Format (1 hour Interval)</Label>
        <TimePicker withSearch={true} interval={60} id="12-hour" />
      </div>

      <div className="w-25 ml-7">
        <Label>24 Hour Format (1 hour Interval)</Label>
        <TimePicker timeFormat="24-Hour" withSearch={true} interval={60} id="24-hour" />
      </div>
    </Row>
  );
}
```


#### TimePicker

```jsx
import { Row, Label, DatePicker, TimePicker } from '@innovaccer/design-system';

() => {

  const [open, setOpen] = React.useState(false);

  const handleDateChange = (date) => {
    if(date) {
      setOpen(false);
      setTimeout(() => {
        setOpen(true);
      }, 0);
    }
  };

  return (
    <Row>
      <div className="w-25">
        <Label>Date</Label>
        <DatePicker
          firstDayOfWeek="saturday"
          onDateChange={handleDateChange}
          outputFormat="yyyy/mm/dd"
          withInput={true}
          inputOptions={{
            required: true,
          }}
        />
      </div>
      <div className="w-25 ml-7">
        <Label>Time</Label>
        <TimePicker withSearch={true} open={open} />
      </div>
    </Row>
  );
}
```


#### TimePicker

```jsx
import { Row, Label, TimePicker } from '@innovaccer/design-system';

() => {

  const onChangeHandler = (props) => {
    console.log(props);
  };

  return (
    <Row>
      <div className="w-25">
        <Label>12 Hour Format</Label>
        <TimePicker 
          withSearch={true} 
          startTime="00:00 AM" 
          endTime="11:59 PM" 
          onChange={onChangeHandler} 
          noResultMessage="Invalid Time"
          id="12-hour"
        />
      </div>
      <div className="w-25 ml-7">
        <Label>24 Hour Format</Label>
        <TimePicker
          withSearch={true}
          startTime="00:00 AM"
          endTime="11:59 PM"
          timeFormat="24-Hour"
          onChange={onChangeHandler}
          noResultMessage="Invalid Time"
          id="24-hour"
        />
      </div>
  </Row>
  );
}
```


#### TimePicker

```jsx
import { Label, TimePicker, HelpText } from '@innovaccer/design-system';

() => {

  const onChangeHandler = (props) => {
    console.log(props);
  };

  return (
    <div className="w-25">
      <Label>Time</Label>
      <TimePicker
        withSearch={true}
        startTime="00:00 AM"
        endTime="11:59 PM"
        onChange={onChangeHandler}
        noResultMessage="Invalid Time"
        id="12-hour"
        error={true}
      />
      <HelpText error={true} message={'Error message goes here.'} />
    </div>
  );
}
```# Toast

Toasts are used to notify users about the outcome of their actions without disrupting the ongoing user workflow.

### Code Examples

#### Components Toast All

```jsx
import { Toast } from '@innovaccer/design-system';

() => {
  const title = 'Sample toast';

  const message = '';

  const actionLabel1 = '';
  const actionLabel2 = '';

  const props = {
    actions: [],
  };

  if (actionLabel1) {
    props.actions.push({
      label: actionLabel1,
      onClick: () => action('action button click: 1')(),
    });
  }
  if (actionLabel2) {
    props.actions.push({
      label: actionLabel2,
      onClick: () => action('action button click: 2')(),
    });
  }

  return <Toast title={title} message={message} onClose={action('on-close clicked')} {...props} />;
}
```


#### Components Toast Alert Toast

```jsx
import { Toast } from '@innovaccer/design-system';

() => (
  <Toast
    appearance="alert"
    title="Campaign failed to run"
    message="Try to run again. If it continues to fail, please raise a ticket."
  />
)
```


#### Components Toast Info Toast

```jsx
import { Toast } from '@innovaccer/design-system';

() => (
  <Toast
    appearance="info"
    title="Sophie sent you a task"
    message="Schedule Appointment for 'Joy Lawson'. It's due on Aug 31."
  />
)
```


#### Components Toast Success Toast

```jsx
import { Toast } from '@innovaccer/design-system';

() => (
  <Toast
    appearance="success"
    title="Outreach successfully sent"
    message="2,340 outreach messages have been successfully sent."
  />
)
```


#### Components Toast Toast With Actions

```jsx
import { Toast } from '@innovaccer/design-system';

() => (
  <Toast
    appearance="success"
    title="Review requested successfully"
    message="Automatically redirecting to the next Prior Auth of Joy Lawson in 10s"
    actions={[
      {
        label: 'Need Prior Auth',
        onClick: () => {},
      },
      {
        label: 'Go To Worklist',
        onClick: () => {},
      },
    ]}
  />
)
```


#### Components Toast Toast With Description

```jsx
import { Toast } from '@innovaccer/design-system';

() => (
  <Toast appearance="success" title="Message sent successfully" message="Description goes here" />
)
```


#### Toast

```jsx
import { Toast } from '@innovaccer/design-system';

() => {
  const appearances = ['info', 'success', 'alert', 'warning'];
  return (
    <div className="d-flex flex-column">
      {appearances.map((appear, ind) => {
        return (
          <div key={ind} className="mr-5 mb-8">
            <Toast appearance={appear} title={appear.charAt(0).toUpperCase() + appear.slice(1)} />
          </div>
        );
      })}
    </div>
  );
}
```


#### Toast

```jsx
import { Toast } from '@innovaccer/design-system';

() => {
  const appearances = ['info', 'success', 'alert', 'warning'];

  const message = 'Outreach was sent';

  const actionLabel1 = 'Try Again';
  const actionLabel2 = '';

  const props = {
    actions: [],
  };

  if (actionLabel1) {
    props.actions.push({
      label: actionLabel1,
      onClick: () => action('action button click: 1')(),
    });
  }
  if (actionLabel2) {
    props.actions.push({
      label: actionLabel2,
      onClick: () => action('action button click: 2')(),
    });
  }

  return (
    <div className="d-flex flex-column">
      {appearances.map((appearance, ind) => {
        return (
          <div key={ind} className="mr-5 mb-8">
            <Toast
              appearance={appearance}
              title={appearance.charAt(0).toUpperCase() + appearance.slice(1)}
              message={message}
              onClose={action('on-close clicked')}
              {...props}
            />
          </div>
        );
      })}
    </div>
  );
}
```


#### Toast

```jsx
import { Toast } from '@innovaccer/design-system';

() => {
  const appearances = ['info', 'success', 'alert', 'warning'];

  const message = 'Outreach was sent';
  return (
    <div className="d-flex flex-column">
      {appearances.map((appearance, ind) => {
        return (
          <div key={ind} className="mr-5 mb-8">
            <Toast
              appearance={appearance}
              title={appearance.charAt(0).toUpperCase() + appearance.slice(1)}
              message={message}
            />
          </div>
        );
      })}
    </div>
  );
}
```


#### Components Toast Warning Toast

```jsx
import { Toast } from '@innovaccer/design-system';

() => (
  <Toast
    appearance="warning"
    title="Chat response is delayed"
    message="'Memorial Clinic' has been running for more that 2 hours."
  />
)
```# Tooltip

Tooltip is used to display content in relation to a target when that target is hovered.

### Code Examples

#### Components Tooltip All

```jsx
import { Tooltip, Button } from '@innovaccer/design-system';

() => {
  const position = 'bottom';
  const appendToBody = true;
  const hoverable = false;
  const tooltip = 'An awesome tooltip';

  const options = {
    tooltip,
    hoverable,
    position,
    appendToBody,
  };

  return (
    <div className="mb-8 ml-14">
      <Tooltip {...options}>
        <Button>Hover over me</Button>
      </Tooltip>
    </div>
  );
}
```


#### Tooltip

```jsx
import { Tooltip, Text, Avatar } from '@innovaccer/design-system';

() => {
  const [showTooltip, setShowTooltip] = React.useState(false);
  const elementRef = React.useRef(null);
  return (
    <div className="d-flex justify-content-around">
      <div>
        <Tooltip showOnTruncation={true} tooltip="show me the tooltip on hover">
          <Text style={{ maxWidth: 150 }} className="ellipsis--noWrap d-inline-block w-100">
            show me the tooltip on hover
          </Text>
        </Tooltip>
      </div>
      <div>
        <Tooltip showOnTruncation={true} tooltip="Don't show me the tooltip">
          <Text style={{ maxWidth: 300 }} className="ellipsis--noWrap d-inline-block w-100">
            Don't show me the tooltip on hover
          </Text>
        </Tooltip>
      </div>
      <div>
        <Tooltip
          elementRef={elementRef}
          showOnTruncation={true}
          tooltip="John Doe: Passionate Innovator and Visionary Leader"
        >
          <div className="d-flex ellipsis--noWrap">
            <Avatar appearance="primary" withTooltip={false} firstName="John" lastName="Doe" size="tiny" />
            <Text style={{ maxWidth: 200 }} ref={elementRef} className="ellipsis--noWrap w-100 ml-3 mt-2">
              John Doe: Passionate Innovator and Visionary Leader
            </Text>
          </div>
        </Tooltip>
      </div>
    </div>
  );
}
```


#### Tooltip

```jsx
import { Tooltip, Avatar, Text } from '@innovaccer/design-system';

() => {
  const [isFirstTruncated, setIsFirstTruncated] = React.useState(false);
  const [isSecondTruncated, setIsSecondTruncated] = React.useState(false);

  const { detectTruncation } = Tooltip.useAutoTooltip();
  const firstContentRef = React.useRef(null);
  const SecondContentRef = React.useRef(null);

  React.useEffect(() => {
    const isFirstTruncated = detectTruncation(firstContentRef);
    const isSecondTruncated = detectTruncation(SecondContentRef);
    setIsFirstTruncated(isFirstTruncated);
    setIsSecondTruncated(isSecondTruncated);
  }, [firstContentRef, SecondContentRef]);

  return (
    <div className="d-flex justify-content-around">
      <div>
        <Tooltip showTooltip={isFirstTruncated} tooltip="John Doe: Passionate Innovator and Visionary Leader">
          <div className="d-flex ellipsis--noWrap">
            <Avatar appearance="primary" withTooltip={false} firstName="John" lastName="Doe" size="tiny" />
            <Text ref={firstContentRef} style={{ maxWidth: 150 }} className="ellipsis--noWrap w-100 ml-3 mt-2">
              John Doe: Passionate Innovator and Visionary Leader
            </Text>
          </div>
        </Tooltip>
      </div>
      <div>
        <Tooltip showTooltip={isSecondTruncated} tooltip="John Doe: Passionate Innovator and Visionary Leader">
          <div className="d-flex ellipsis--noWrap">
            <Avatar appearance="primary" withTooltip={false} firstName="John" lastName="Doe" size="tiny" />
            <Text ref={SecondContentRef} className="ellipsis--noWrap w-100 ml-3 mt-2">
              John Doe: Passionate Innovator and Visionary Leader
            </Text>
          </div>
        </Tooltip>
      </div>
    </div>
  );
}
```


#### Tooltip

```jsx
import { Tooltip, Button } from '@innovaccer/design-system';

() => {
  const positions = ['top', 'top-start', 'bottom', 'top-end', 'bottom-start', 'bottom-end', 'right', 'left'];
  const appendToBody = false;
  const tooltip = 'An awesome tooltip';

  const options = {
    tooltip,
    appendToBody,
  };

  return (
    <div className="pb-6 Row">
      {positions.map((pos, ind) => {
        return (
          <div key={ind} className="mr-13 mt-8">
            <Tooltip position={pos} {...options}>
              <Button>{pos}</Button>
            </Tooltip>
          </div>
        );
      })}
    </div>
  );
}
```


#### Tooltip

```jsx
import { Label, Switch, Tooltip, Button } from '@innovaccer/design-system';

() => {
  const [showTooltip, setShowTooltip] = React.useState(false);

  return (
    <div>
      <div className="mb-6 d-flex">
        <Label className="mr-4">Show Tooltip</Label>
        <Switch
          value={showTooltip}
          aria-label="Toggle tooltip"
          size="tiny"
          onChange={(_, selected) => setShowTooltip(selected)}
        />
      </div>

      <Tooltip showTooltip={showTooltip} tooltip="An awesome tooltip">
        <Button>Conditional Tooltip</Button>
      </Tooltip>
    </div>
  );
}
```# VerificationCodeInput



### Code Examples

#### Input

```jsx
import { Label, VerificationCodeInput } from '@innovaccer/design-system';

() => {
  const inputType = 'number';

  const fields = undefined;

  const value = '6543';

  const placeholder = '-';

  const disabled = false;

  const autoFocus = true;

  const readOnly = false;

  const error = false;

  const pattern = '';

  return (
    <>
      <Label withInput={true}>Verification code</Label>
      <VerificationCodeInput
        fields={fields}
        type={inputType}
        value={value}
        disabled={disabled}
        readOnly={readOnly}
        onChange={action('on-change')}
        onComplete={action('on-complete')}
        onFocus={action('on-focus')}
        onBlur={action('on-blur')}
        placeholder={placeholder}
        error={error}
        pattern={pattern}
        // TODO(a11y)
        
        autoFocus={autoFocus}
      />
    </>
  );
}
```


#### VerificationCodeInput

```jsx
import { Label, VerificationCodeInput } from '@innovaccer/design-system';

() => {
  return (
    <>
      <Label withInput={true}>Verification code</Label>
      <VerificationCodeInput disabled={true} value="1234" />
    </>
  );
}
```


#### VerificationCodeInput

```jsx
import { Label, VerificationCodeInput } from '@innovaccer/design-system';

() => {
  return (
    <>
      <Label withInput={true}>Verification code</Label>
      <VerificationCodeInput error={true} />
    </>
  );
}
```


#### Input

```jsx
import { Label, VerificationCodeInput } from '@innovaccer/design-system';

() => {
  return (
    <>
      <Label withInput={true}>Verification code</Label>
      <VerificationCodeInput />
    </>
  );
}
```


#### Input

```jsx
import { Label, VerificationCodeInput, Button } from '@innovaccer/design-system';

() => {
    const inputType = 'number';
  
    const fields = undefined;
  
    const placeholder = '-';
  
    const disabled = false;
  
    const autoFocus = true;
  
    const readOnly = false;
  
    const error = false;
  
    const pattern = '';
    const [counter, setCounter] = React.useState(0);
    const [value, setValue] = React.useState('1234');
    const handleClick = () => {
      setCounter(counter + 1);
      setValue('----');
    };
  
    return (
      <>
        <Label withInput={true}>Verification code</Label>
        <VerificationCodeInput
          key={counter}
          fields={fields}
          type={inputType}
          value={value}
          disabled={disabled}
          readOnly={readOnly}
          onComplete={console.log('on-complete')}
          onFocus={console.log('on-focus')}
          onBlur={console.log('on-blur')}
          placeholder={placeholder}
          error={error}
          pattern={pattern}
          // TODO(a11y)
          //  eslint-disable-next-line
          autoFocus={autoFocus}
        />
        <Button className="mt-5" onClick={handleClick}>
          Reset
        </Button>
      </>
    );
  }
```


#### Input

```jsx
import { Label, VerificationCodeInput } from '@innovaccer/design-system';

() => {
  return (
    <>
      <Label withInput={true}>Verification code</Label>
      <VerificationCodeInput fields={6} />
    </>
  );
}
```# VerticalNav



### Code Examples

#### Components VerticalNav VerticalNav All

```jsx
import { VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'patient_360',
      label: 'Patient 360',
      icon: 'assignment_ind',
      link: '/patient360',
      count: 10,
    },
    {
      name: 'care_management',
      label: 'Care Management and Resources',
      icon: 'forum',
      count: 2,
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      disabled: true,
      icon: 'airline_seat_flat_angled',
      count: 5,
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite',
      subMenu: [
        {
          name: 'risk.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'risk.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'receipt'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'account_circle'
    },
    {
      name: 'manual_entry',
      label: 'Manual Entry',
      icon: 'border_color'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    }
  ];

  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return (
    <div className="bg-secondary-lightest vh-100">
      <VerticalNav
        menus={data}
        expanded={true}
        active={active}
        onClick={onClickHandler}
        hoverable={false}
      />
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Child Items With Icons

```jsx
import { Collapsible, VerticalNav } from '@innovaccer/design-system';

() => {

  const data = [
    {
      name: 'clinical_data',
      label: 'Clinical Data',
      icon: 'assignment_ind'
    },
    {
      name: 'care_management',
      label: 'Care Management',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'people'
        },
        {
          name: 'care_management.care_protocol',
          label: 'Care Protocol',
          icon: 'fact_check'
        },
        {
          name: 'care_management.assessments',
          label: 'Assessments',
          icon: 'assessment'
        },
        {
          name: 'care_management.tasks',
          label: 'Tasks',
          icon: 'alarm'
        },
        {
          name: 'care_management.goals',
          label: 'Goals',
          icon: 'golf_course'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'accessibility_new'
        },
        {
          name: 'care_management.medical_adherence',
          label: 'Medical Adherence',
          icon: 'local_pharmacy'
        },
        {
          name: 'care_management.community_resources',
          label: 'Community Resources',
          icon: 'businesses'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite'
    },
    {
      name: 'preventive_health',
      label: 'Preventive Health',
      icon: 'beenhere'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'receipt'
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'account_circle'
    },
    {
      name: 'manual_entry',
      label: 'Manual Entry',
      icon: 'edit'
    },
    {
      name: 'patient_notes',
      label: 'Patient Notes',
      icon: 'note_add'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    },
  ];

  const [expanded, setExpanded] = React.useState(false);
  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  return (
    <div className="bg-secondary-lightest vh-100">
      <Collapsible expanded={expanded} onToggle={setExpanded}>
        <VerticalNav
          menus={data}
          active={active}
          expanded={expanded}
          onClick={setActive}
        />
      </Collapsible>
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Custom Items Renderer

```jsx
import { Icon, Tooltip, Text, VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'clinical_data',
      label: 'Clinical Data',
      icon: 'assignment_ind'
    },
    {
      name: 'care_management',
      label: 'Care Management',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'people'
        },
        {
          name: 'care_management.care_protocol',
          label: 'Care Protocol',
          icon: 'fact_check'
        },
        {
          name: 'care_management.assessments',
          label: 'Assessments',
          icon: 'assessment'
        },
        {
          name: 'care_management.tasks',
          label: 'Tasks',
          icon: 'alarm'
        },
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite'
    },
    {
      name: 'preventive_health',
      label: 'Preventive Health',
      icon: 'beenhere'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'receipt'
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'account_circle'
    },
    {
      name: 'manual_entry',
      label: 'Manual Entry',
      icon: 'edit'
    },
    {
      name: 'patient_notes',
      label: 'Patient Notes',
      icon: 'note_add'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    },
  ];

  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  const customItemRenderer = (props) => {
    const {menu, onClick, expanded, isChildren} = props;
    return ( 
      <div 
        onClick={() => onClick(menu)}
        className={`p-5 d-flex align-items-center cursor-pointer ${isChildren ? 'ml-7' : ''}`}
      >
        {menu.icon && 
            <Icon
              data-test="DesignSystem-VerticalNav--Icon"
              className={expanded ? 'mr-4' : ''}
              name={menu.icon}
            />
        }
        <Tooltip tooltip={menu.label} position="right">
          <Text weight="medium">
            {menu.label}
          </Text>
        </Tooltip>
      </div>
    );
  };
  
  return (
    <div className="bg-secondary-lightest vh-100">
      <VerticalNav
        menus={data}
        expanded={true}
        active={active}
        onClick={setActive}
        customItemRenderer={customItemRenderer}
      />
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Custom Options Renderer

```jsx
import { Tooltip, Icon, VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'clinical_data',
      label: 'Clinical Data',
      icon: 'assignment_ind'
    },
    {
      name: 'care_management',
      label: 'Care Management policies',
      icon: 'forum',
      count: 40,
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'people',
          count: 10
        },
        {
          name: 'care_management.care_protocol',
          label: 'Care Protocol',
          icon: 'fact_check',
          count: 10
        },
        {
          name: 'care_management.assessments',
          label: 'Assessments',
          icon: 'assessment',
          count: 10
        },
        {
          name: 'care_management.tasks',
          label: 'Tasks',
          icon: 'alarm',
          count: 10
        },
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      icon: 'airline_seat_flat_angled',
      count: 100
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite'
    },
    {
      name: 'preventive_health',
      label: 'Preventive Health',
      icon: 'beenhere'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'receipt'
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'account_circle'
    },
    {
      name: 'manual_entry',
      label: 'Manual Entry',
      icon: 'edit'
    },
    {
      name: 'patient_notes',
      label: 'Patient Notes',
      icon: 'note_add'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    },
  ];

  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  const customItemRenderer = (props) => {
    const {menu, onClick, hasSubmenu, expanded, contentRef, isChildren, MenuIcon, MenuLabel, MenuPills} = props;
    const [isTextTruncated, setIsTextTruncated] = React.useState(false);
    const { detectTruncation } = Tooltip.useAutoTooltip();
  
    React.useEffect(() => {
      const isTruncated = detectTruncation(contentRef);
      setIsTextTruncated(isTruncated);
      console.log(isTruncated);
    }, []);

    return ( 
      <Tooltip showTooltip={isTextTruncated} tooltip={menu.label} position="right">
      <div 
        onClick={() => onClick(menu)}
        style={{width: '232px'}}
        className={`p-5 d-flex align-items-center cursor-pointer ${isChildren ? 'ml-7' : ''}`}
      >
        {menu.icon && (
          <Icon data-test="DesignSystem-VerticalNav--Icon" className={expanded ? 'mr-4' : ''} name={menu.icon} />
        )}
        {MenuLabel()}
        <div className="ml-5 d-flex">{MenuPills()}</div>
        {hasSubmenu && MenuIcon()}
      </div>
      </Tooltip>
    );
  };
  
  return (
    <div className="bg-secondary-lightest vh-100">
      <VerticalNav
        menus={data}
        expanded={true}
        active={active}
        onClick={setActive}
        customItemRenderer={customItemRenderer}
      />
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Custom Trigger

```jsx
import { Icon, Heading, Collapsible, VerticalNav } from '@innovaccer/design-system';

() => {
  const [expanded, setExpanded] = React.useState(false);
  const [active, setActive] = React.useState({
    name: 'TODOs.Due',
  });

  const data = [
    {
      name: 'TODOs',
      label: 'TODOs',
      icon: 'assignment_ind',
      count: 31,
      subMenu: [
        {
          name: 'TODOs.Due',
          label: 'Due',
          count: 31
        },
        {
          name: 'TODOs.Completed',
          label: 'Completed',
          count: 0
        },
      ],
    },
    {
      name: 'Received',
      label: 'Received',
      count: 0
    },
    {
      name: 'Sent',
      label: 'Sent',
      count: 5
    },
  ];

  return (
    <div>
      <div className='d-flex align-items-center mb-3'>
        <Icon name="menu" className="cursor-pointer" onClick={() => setExpanded(!expanded) }></Icon>
        <Heading size='s' className="ml-4">My Worklist</Heading>
      </div>
      <Collapsible withTrigger={false} expanded={expanded} height="100vh">
        <VerticalNav menus={data} active={active} expanded={expanded} onClick={setActive} />
      </Collapsible>
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Custom Vertical Navigation

```jsx
import { Collapsible, DatePicker, VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'to_dos',
      label: 'To-dos',
      icon: 'check_circle_outline',
      subMenu: [
        {
          name: 'to_dos.due',
          label: 'Due',
          count: 10
        },
        {
          name: 'to_dos.completed',
          label: 'Completed',
          count: 7
        },
      ]
    },
    {
      name: 'received',
      label: 'Received',
      icon: 'call_received'
    },
    {
      name: 'sent',
      label: 'Sent',
      icon: 'call_made'
    },
  ];

  const [expanded, setExpanded] = React.useState(true);
  const [active, setActive] = React.useState({
    name: 'data_exchange.reports'
  });

  return (
    <div className="bg-secondary-lightest vh-100">
      <Collapsible expanded={expanded} onToggle={setExpanded} hoverable={false}>
        <>
        {expanded && (
          <div className="mt-5 d-flex justify-content-center border-top">
          <DatePicker date={new Date()} size="small" />
          </div>
          )}
          <VerticalNav
            menus={data}
            expanded={expanded}
            active={active}
            onClick={setActive}
          />
        </>
      </Collapsible>
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Flat Edged Vertical Navigation

```jsx
import { Collapsible, VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'home',
      label: 'Home',
      icon: 'home',
      count: 10
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'account_circle',
      count: 25,
      subMenu: [
        {
          name: 'profile.personal',
          label: 'Personal',
          count: 5
        },
        {
          name: 'profile.are_team',
          label: 'Care Team',
          count: 10
        },
        {
          name: 'profile.goals',
          label: 'Goals',
          count: 5
        },
        {
          name: 'profile.care_plans',
          label: 'Care Plans',
          count: 5
        }
      ]
    },
    {
      name: 'medical_records',
      label: 'Medical Records',
      icon: 'local_hospital',
      subMenu: [
        {
          name: 'medical_records.allergies',
          label: 'Allergies'
        },
        {
          name: 'medical_records.conditions',
          label: 'Conditions'
        },
        {
          name: 'medical_records.immunizations',
          label: 'Immunizations'
        },
        {
          name: 'medical_records.lab_results',
          label: 'Lab Results'
        },
        {
          name: 'medical_records.medications',
          label: 'Medications'
        },
        {
          name: 'medical_records.procedures',
          label: 'Procedures'
        },
        {
          name: 'medical_records.vitals',
          label: 'Vitals'
        },
        {
          name: 'medical_records.smoking_history',
          label: 'medical_records.Smoking History'
        },
        {
          name: 'devices',
          label: 'Devices'
        }
      ]
    },
    {
      name: 'formulary',
      label: 'Formulary',
      icon: 'list',
    },
    {
      name: 'encounters',
      label: 'Encounters',
      icon: 'directions_walk',
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'receipt'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    },
    {
      name: 'find_care',
      label: 'Find Care',
      icon: 'search',
      subMenu: [
        {
          name: 'find_care.providers',
          label: 'Providers'
        },
        {
          name: 'find_care.pharmacies',
          label: 'Pharmacies'
        },
      ]
    },
    {
      name: 'connected_applications',
      label: 'Connected Applications',
      icon: 'extension'
    },
  ];

  const [expanded, setExpanded] = React.useState(true);
  const [active, setActive] = React.useState({
    name: 'medical_records.allergies'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return (
    <div className="bg-secondary-lightest vh-100">
      <Collapsible expanded={expanded} onToggle={setExpanded} hoverable={false}>
        <VerticalNav
          menus={data}
          active={active}
          expanded={expanded}
          onClick={onClickHandler}
        />
      </Collapsible>
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Grouping

```jsx
import { VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'customer_information',
      label: 'Customer Information',
      group: 'General'
    },
    {
      name: 'organizational_structure',
      label: 'Organizational Structure',
      group: 'General'
    },
    {
      name: 'contacts',
      label: 'Contacts',
      group: 'General',
    },
    {
      name: 'empi',
      label: 'EMPI',
      group: 'Platform',
    },
    {
      name: 'data_exchange',
      label: 'Data Exchange',
      group: 'Platform',
      subMenu: [
        {
          name: 'data_exchange.reports',
          label: 'Reports'
        },
        {
          name: 'data_exchange.destinations',
          label: 'Destinations'
        },
        {
          name: 'data_exchange.validation',
          label: 'Validation'
        },
      ]
    },
    {
      name: 'import_export_settings',
      label: 'Import/Export Settings',
      group: 'Platform',
    },
    {
      name: 'pipelines',
      label: 'Pipelines',
      group: 'Apps',
    },
  ];

  const [active, setActive] = React.useState({
    name: 'data_exchange.reports'
  });

  return (
    <div className="bg-secondary-lightest vh-100">
      <VerticalNav
        menus={data}
        expanded={true}
        active={active}
        onClick={setActive}
      />
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Hoverable Vertical Navigation

```jsx
import { Collapsible, VerticalNav, Heading, Card, Table } from '@innovaccer/design-system';

() => {
  const tableData = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: '40%',
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      filters: [
        { label: 'A-G', value: 'a-g' },
        { label: 'H-R', value: 'h-r' },
        { label: 'S-Z', value: 's-z' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          switch (filter) {
            case 'a-g':
              if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
              break;
            case 'h-r':
              if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
              break;
            case 's-z':
              if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
              break;
          }
        }
        return false;
      },
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
      cellType: 'WITH_META_LIST'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
      filters: [
        { label: 'Male', value: 'male' },
        { label: 'Female', value: 'female' },
      ],
      onFilterChange: (a, filters) => {
        for (const filter of filters) {
          if (a.gender.toLowerCase() === filter) return true;
        }
        return false;
      },
    },
  ];

  const data = [
    {
      name: 'clinical_data',
      label: 'Clinical Data',
      icon: 'assignment_ind'
    },
    {
      name: 'care_management',
      label: 'Care Management Policies',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'people'
        },
        {
          name: 'care_management.care_protocol',
          label: 'Care Protocol',
          icon: 'fact_check'
        },
        {
          name: 'care_management.assessments',
          label: 'Assessments',
          icon: 'assessment'
        },
        {
          name: 'care_management.tasks',
          label: 'Tasks',
          icon: 'alarm'
        },
        {
          name: 'care_management.goals',
          label: 'Goals',
          icon: 'golf_course'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'accessibility_new'
        },
        {
          name: 'care_management.medical_adherence',
          label: 'Medical Adherence',
          icon: 'local_pharmacy'
        },
        {
          name: 'care_management.community_resources',
          label: 'Community Resources',
          icon: 'businesses'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite'
    },
    {
      name: 'preventive_health',
      label: 'Preventive Health',
      icon: 'beenhere'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'receipt'
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'account_circle'
    },
    {
      name: 'manual_entry',
      label: 'Manual Entry',
      icon: 'edit'
    },
    {
      name: 'patient_notes',
      label: 'Patient Notes',
      icon: 'note_add'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    },
  ];

  const [expanded, setExpanded] = React.useState(false);
  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  return (
    <div className="d-flex bg-secondary-lightest vh-100">
      <Collapsible expanded={expanded} onToggle={setExpanded}>
        <VerticalNav
          menus={data}
          active={active}
          expanded={expanded}
          onClick={setActive}
        />
      </Collapsible>
      <div className="ml-6 d-flex flex-column">
        <Heading className="my-5">Assessments</Heading>
        <Card className="h-100 overflow-hidden">
          <Table
            data={tableData}
            schema={schema}
            withHeader={true}
            withCheckbox={true}
            headerOptions={{
              withSearch: true
            }}
            onSearch={(currData, searchTerm) => {
              return currData.filter(d =>
                d.firstName.toLowerCase().match(searchTerm.toLowerCase())
                || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
              );
            }}
            withPagination={true}
            pageSize={5}
          />
        </Card>
      </div>
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Label Overflow Behaviour

```jsx
import { VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'clinical_data',
      label: 'Clinical Data',
      icon: 'assignment_ind'
    },
    {
      name: 'care_management',
      label: 'Care Management Timeline Protocol',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'people'
        },
        {
          name: 'care_management.care_protocol',
          label: 'Care Protocol Management Guidelines',
          icon: 'fact_check'
        },
        {
          name: 'care_management.assessments',
          label: 'Assessments',
          icon: 'assessment'
        },
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'preventive_health',
      label: 'Preventive Health Precautions Template',
      icon: 'beenhere'
    },
  ];

  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });
  
  return (
    <div className="bg-secondary-lightest vh-100">
      <VerticalNav
        menus={data}
        expanded={true}
        active={active}
        onClick={setActive}   
      />
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Non Collapsible Vertical Navigation

```jsx
import { VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'practice',
      label: 'Practice',
    },
    {
      name: 'users',
      label: 'Users',
    },
    {
      name: 'copayment',
      label: 'Copayment',
    },
    {
      name: 'subscription',
      label: 'Subscription',
    },
    {
      name: 'import_export_settings',
      label: 'Import/Export Settings',
    },
  ];

  const [active, setActive] = React.useState({
    name: 'users'
  });

  return (
    <div className="bg-secondary-lightest pb-12">
      <VerticalNav
        menus={data}
        active={active}
        expanded={true}
        onClick={setActive}
      />
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Round Edged Vertical Navigation

```jsx
import { VerticalNav } from '@innovaccer/design-system';

() => {

  const primaryNavdata = [
    {
      name: 'clinical_data',
      label: 'Clinical Data',
      icon: 'assignment_ind'
    },
    {
      name: 'care_management',
      label: 'Care Management',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'people'
        },
        {
          name: 'care_management.care_protocol',
          label: 'Care Protocol',
          icon: 'fact_check'
        },
        {
          name: 'care_management.assessments',
          label: 'Assessments',
          icon: 'assessment'
        },
        {
          name: 'care_management.tasks',
          label: 'Tasks',
          icon: 'alarm'
        },
        {
          name: 'care_management.goals',
          label: 'Goals',
          icon: 'golf_course'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'accessibility_new'
        },
        {
          name: 'care_management.medical_adherence',
          label: 'Medical Adherence',
          icon: 'local_pharmacy'
        },
        {
          name: 'care_management.community_resources',
          label: 'Community Resources',
          icon: 'businesses'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite'
    },
    {
      name: 'preventive_health',
      label: 'Preventive Health',
      icon: 'beenhere'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'receipt'
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'account_circle'
    },
    {
      name: 'manual_entry',
      label: 'Manual Entry',
      icon: 'edit'
    },
    {
      name: 'patient_notes',
      label: 'Patient Notes',
      icon: 'note_add'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    },
  ];

  const secondaryNavdata = [
    {
      name: '11/12/20',
      label: '11 Dec, 2020',
    },
    {
      name: '17/11/20',
      label: '17 Nov, 2020',
    },
    {
      name: '07/11/20',
      label: '7 Nov, 2020',
    },
    {
      name: '09/10/20',
      label: '9 Oct, 2020',
    },
    {
      name: '23/08/20',
      label: '23 Aug, 2020',
    },
  ];

  const [primaryActive, setPrimaryActive] = React.useState({
    name: 'care_management.timeline'
  });

  const [secondaryActive, setSecondaryActive] = React.useState({
    name: '11/12/20'
  });

  return (
    <div className="d-flex bg-secondary-lightest vh-100">
      <VerticalNav
        menus={primaryNavdata}
        active={primaryActive}
        onClick={setPrimaryActive}
      />
      <VerticalNav
        menus={secondaryNavdata}
        active={secondaryActive}
        rounded={true}
        className="mt-10 ml-5"
        onClick={setSecondaryActive}
      />
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Secondary Vertical Navigation

```jsx
import { VerticalNav, Heading, Card } from '@innovaccer/design-system';

() => {

  const primaryNavdata = [
    {
      name: 'clinical_data',
      label: 'Clinical Data',
      icon: 'assignment_ind'
    },
    {
      name: 'care_management',
      label: 'Care Management',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'people'
        },
        {
          name: 'care_management.care_protocol',
          label: 'Care Protocol',
          icon: 'fact_check'
        },
        {
          name: 'care_management.assessments',
          label: 'Assessments',
          icon: 'assessment'
        },
        {
          name: 'care_management.tasks',
          label: 'Tasks',
          icon: 'alarm'
        },
        {
          name: 'care_management.goals',
          label: 'Goals',
          icon: 'golf_course'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'accessibility_new'
        },
        {
          name: 'care_management.medical_adherence',
          label: 'Medical Adherence',
          icon: 'local_pharmacy'
        },
        {
          name: 'care_management.community_resources',
          label: 'Community Resources',
          icon: 'businesses'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite'
    },
    {
      name: 'preventive_health',
      label: 'Preventive Health',
      icon: 'beenhere'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'receipt'
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'account_circle'
    },
    {
      name: 'manual_entry',
      label: 'Manual Entry',
      icon: 'edit'
    },
    {
      name: 'patient_notes',
      label: 'Patient Notes',
      icon: 'note_add'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    },
  ];

  const secondaryNavdata = [
    {
      name: '19/01/20',
      label: '19 Jan, 2020',
      group: 'Completed'
    },
    {
      name: '16/01/20',
      label: '16 Jan, 2020',
      group: 'Completed'
    },
    {
      name: '11/11/20',
      label: '11 Nov, 2020',
      group: 'Ongoing'
    },
    {
      name: '17/11/20',
      label: '17 Nov, 2020',
      group: 'Ongoing'
    },
    {
      name: '07/11/20',
      label: '7 Nov, 2020',
      group: 'Ongoing'
    },
    {
      name: '09/10/20',
      label: '9 Oct, 2020',
      group: 'Ongoing'
    },
    {
      name: '23/08/20',
      label: '23 Aug, 2020',
      group: 'Ongoing'
    },
  ];

  const [primaryActive, setPrimaryActive] = React.useState({
    name: 'care_management.timeline'
  });

  const [secondaryActive, setSecondaryActive] = React.useState({
    name: '19/01/20'
  });

  return (
    <div className="d-flex bg-secondary-lightest vh-100">
      <VerticalNav
        menus={primaryNavdata}
        active={primaryActive}
        onClick={setPrimaryActive}
      />
      <div className="w-100 ml-6">
        <Heading className="my-5">Assessments</Heading>
        <Card shadow="none pb-12">
          <VerticalNav
            menus={secondaryNavdata}
            active={secondaryActive}
            onClick={setSecondaryActive}
          />
        </Card>
      </div>
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Variants Rounded

```jsx
import { VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'patient_360',
      label: 'Patient 360',
      icon: 'assignment_ind',
      link: '/patient360'
    },
    {
      name: 'care_management',
      label: 'Care Management and Resources',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      disabled: true,
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite',
      subMenu: [
        {
          name: 'risk.timeline',
          label: 'Timeline'
        },
        {
          name: 'risk.care_plans',
          label: 'Care Plans'
        }
      ]
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'receipt'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'account_circle'
    },
    {
      name: 'manula_entry',
      label: 'Manual Entry',
      icon: 'border_color'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    }
  ];

  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });
  const [expanded, setExpanded] = React.useState(false);

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return (
    <div className="bg-secondary-lightest vh-100">
      <VerticalNav
        menus={data}
        expanded={true}
        active={active}
        rounded={true}
        onClick={onClickHandler}
      />
    </div>
  );
}
```


#### Components VerticalNav VerticalNav Variants Section

```jsx
import { VerticalNav } from '@innovaccer/design-system';

() => {
  const data = [
    {
      name: 'patient_360',
      label: 'Patient 360',
      icon: 'assignment_ind',
      link: '/patient360',
      group: 'Section 1'
    },
    {
      name: 'care_management',
      label: 'Care Management and Resources',
      icon: 'forum',
      group: 'Section 2',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      disabled: true,
      group: 'Section 2',
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite',
      group: 'Section 2',
      subMenu: [
        {
          name: 'risk.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'risk.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'receipt',
      group: 'Section 3'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'account_circle',
      group: 'Section 3'
    },
    {
      name: 'manula_entry',
      label: 'Manual Entry',
      icon: 'border_color',
      group: 'Section 3'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment',
      group: 'Section 3'
    }
  ];

  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return (
    <div className="bg-secondary-lightest vh-100">
      <VerticalNav
        menus={data}
        expanded={true}
        active={active}
        onClick={onClickHandler}
        hoverable={false}
      />
    </div>
  );
}
```# patterns



### Code Examples

#### Date and time picker

```jsx
import { Label, DatePicker, Dropdown } from '@innovaccer/design-system';



() => {
  class DateTimePicker extends React.Component {
    constructor(props) {
      super(props);
      this.state = {
        open: false,
        date: undefined,
        time: undefined
      };
    }

    onDateChange(date, dateVal) {
      this.setState({
        date: dateVal,
        open: !!date
      });
    }

    onPopperToggle(val) {
      this.setState({
        open: val
      });
    }

    onChangeHandler(selected) {
      this.setState({
        time: selected
      });
    }

    render() {
      const timeValues = ['10:00 AM', '10:30 AM', '11:00 AM', '11:30 AM', '12:00 PM', '12:30 PM', '01:00 PM', '01:30 PM'];
      const {
        open
      } = this.state;

      console.log("Date", this.state.date, "Time", this.state.time);

      return (
        <div className="d-flex">
          <div className="d-flex flex-column">
            <Label withInput>Date</Label>
            <DatePicker
              withInput={true}
              onDateChange={this.onDateChange.bind(this)}
            />
          </div>
          <div className="d-flex flex-column ml-5" style={{width: 'var(--spacing-8)'}}>
            <Label withInput>Time</Label>
            <Dropdown
              open={open}
              onPopperToggle={this.onPopperToggle.bind(this)}
              options={timeValues.map(value => ({label: value, value}))}
              onChange={this.onChangeHandler.bind(this)}
            />
          </div>
        </div>
      );
    }
  }

  return <DateTimePicker />
}
```


#### DatePicker

```jsx
import { DatePicker, Subheading, Chip, Divider, Card, Label } from '@innovaccer/design-system';

() => {

  const setDate = (jumpDateIndex) => {
    const d = new Date();
    return d.setDate(d.getDate() + jumpDateIndex);
  };

  const getTomorrowDate = setDate.bind(null, 1);
  const getThreeDaysLaterDate = setDate.bind(null, 3);
  const getOneWeekLaterDate = setDate.bind(null, 7);
  const getThirtyDaysLaterDate = setDate.bind(null, 30);

  
  const DatePickerPreset = ({ size, withInput=false }) => {
    
    const [date, setDate] = React.useState(new Date());
    const [selectedChip, setSelectedChip] = React.useState('today');
    
    const classNames = size === 'small' ? 'd-flex mb-4' : 'd-flex mb-5';
    return (
      <DatePicker date={date} showTodayDate={false} size={size} withInput={withInput}>
        <div className="pt-6 px-5">
          <div className="d-flex align-items-center justify-content-between">
            <Subheading size="s" appearance="subtle">
              Date
            </Subheading>
          </div>
          <div className="pt-4">
            <Chip
              label="Today"
              clearButton={false}
              type="action"
              className={classNames}
              selected={selectedChip === 'today'}
              name="rangePicker"
              onClick={() => {
                setDate(new Date)
                setSelectedChip('today')
              }}
            />
            <Chip
              label="Tomorrow"
              clearButton={false}
              type="action"
              className={classNames}
              name={'chip'}
              onClick={() => {
                setDate(getTomorrowDate())
                setSelectedChip('tomorrow')
              }}
            />
            <Chip
              label="3 days later"
              clearButton={false}
              type="action"
              className={classNames}
              name="rangePicker"
              onClick={() => {
                setDate(getThreeDaysLaterDate())
                setSelectedChip('threeDaysLater')
              }}
            />
            <Chip
              label="1 week later"
              clearButton={false}
              type="action"
              className={classNames}
              name="rangePicker"
              onClick={() => {
                setDate(getOneWeekLaterDate())
                setSelectedChip('oneWeekLater')
              }}
            />
            <Chip
              label="30 days later"
              clearButton={false}
              type="action"
              className={classNames}
              name="rangePicker"
              onClick={() => {
                setDate(getThirtyDaysLaterDate())
                setSelectedChip('thirtyDaysLater')
              }}
            />
          </div>
        </div>
        <Divider vertical={true} />
      </DatePicker>
    );
  };
  return (
    <>
      <Card className="d-inline-flex" shadow="light">
        <DatePickerPreset />
      </Card>
      <Card className="d-inline-flex ml-5" shadow="light">
        <DatePickerPreset size="small" />
      </Card>
      <Card className="w-50 my-5 p-5">
        <Label>Set an appointment date:</Label>
        <DatePickerPreset withInput={true} />
      </Card>
    </>
  );
};
```


#### Date range picker with custom Popover

```jsx
import { Subheading, Icon, Chip, DateRangePicker, Divider } from '@innovaccer/design-system';



() => {
  class CustomPopover extends React.Component {
    constructor(props) {
      super(props);
      const { startDate, endDate } = DateRangePicker.utils.getCurrentWeek();

      this.state = {
        startDate,
        endDate,
        selected: 'currWeek',
        monthNav: DateRangePicker.utils.getCurrentMonth(),
      };

      this.renderChildren = this.renderChildren.bind(this);
      this.setDate = this.setDate.bind(this);
      this.onReset = this.onReset.bind(this);
    }

    setDate(date) {
      const d = new Date();
      return new Date(d.setDate(date));
    }

    onReset() {
      this.setState({
        startDate:null,
        endDate:null,
        selected: "",
        monthNav: DateRangePicker.utils.getCurrentMonth()
      });
    }

    renderChildren() {
      const { startDate, endDate, selected } = this.state;

      return (
        <div className="pt-6 px-5">
          <div className="d-flex align-items-center justify-content-between">
            <Subheading size="s" className="py-3" appearance="subtle">Range</Subheading>
            <Icon name="refresh" onClick={this.onReset} />
          </div>
          <div className="pt-5">
            <Chip
              label="This week"
              clearButton={false}
              type="selection"
              className="mb-5 d-block"
              selected={selected === "currWeek"}
              name="rangePicker"
              onClick={() => {
                this.setState({
                  selected: "currWeek",
                  monthNav: DateRangePicker.utils.getCurrentMonth(),
                  ...DateRangePicker.utils.getCurrentWeek()
                });
              }}
            />
            <Chip
              label="Last week"
              clearButton={false}
              type="selection"
              className="mb-5 d-block"
              selected={selected === 'prevWeek'}
              name={"chip"}
              onClick={() => {
                this.setState({
                  selected: "prevWeek",
                  monthNav: DateRangePicker.utils.getCurrentMonth(),
                  ...DateRangePicker.utils.getPreviousWeek()
                });
              }}
            />
            <Chip
              label="Last month"
              clearButton={false}
              type="selection"
              className="mb-5 d-block"
              selected={selected === 'prevMonth'}
              name="rangePicker"
              onClick={() => {
                this.setState({
                  selected: "prevMonth",
                  monthNav: DateRangePicker.utils.getCurrentMonth() - 1,
                  ...DateRangePicker.utils.getPreviousMonth()
                });
              }}
            />
            <Chip
              label="Last 90 days"
              clearButton={false}
              type="selection"
              className="mb-5 d-block"
              selected={selected === 'prev90Days'}
              name="rangePicker"
              onClick={() => {
                this.setState({
                  selected: "prev90Days",
                  monthNav: DateRangePicker.utils.getCurrentMonth(),
                  ...DateRangePicker.utils.getPrevious90Days()
                });
              }}
            />
            <Chip
              label="Custom"
              clearButton={false}
              type="selection"
              className="mb-5 d-block"
              selected={selected === 'custom'}
              name="rangePicker"
              onClick={() => {
                this.setState({
                  selected: "custom",
                  monthNav: DateRangePicker.utils.getCurrentMonth(),
                  ...DateRangePicker.utils.getCustomDates()
                });
              }}
            />
          </div>
        </div>
      );
    };

    render() {
      const { startDate, endDate, monthNav } = this.state;

      return (
        <div className="w-25">
          <DateRangePicker
            withInput={true}
            singleInput={true}
            startDate={startDate}
            endDate={endDate}
            onRangeChange={(sDate, eDate, sValue, eValue) => {
              console.log(sDate, eDate);
            }}
            monthsInView={1}
            monthNav={monthNav}
          >
            {this.renderChildren()}
            <Divider vertical={true} />
          </DateRangePicker>
        </div>
      )
    }
  }

  return <CustomPopover />
}
```


#### Basic Form

```jsx
import { Card, Heading, Label, Input, Icon, Link, Button } from '@innovaccer/design-system';



() => {
  class BasicForm extends React.Component {

    constructor(props) {
      super(props);

      this.state = {
        signInDisabled: true,
        passwordVisible: false,
        data: { email: '', password: '' }
      };

      this.onEmailChange = this.onEmailChange.bind(this);
      this.onPasswordChange = this.onPasswordChange.bind(this);
      this.onActionClick = this.onActionClick.bind(this);
      this.onSubmit = this.onSubmit.bind(this);
    }

    onActionClick() {
      this.setState({
        passwordVisible: !this.state.passwordVisible
      });
    }

    onEmailChange(event) {
      const { password = '' } = this.state.data;
      const email = event.target.value;
      const disabled = !password || !email;

      this.setState({
        data: { ...this.state.data, email },
        signInDisabled: disabled
      });
    };

    onPasswordChange(event) {
      const { email = '' } = this.state.data;
      const password = event.target.value;
      const disabled = !password || !email;

      this.setState({
        data: { ...this.state.data, password },
        signInDisabled: disabled
      });
    }

    onSubmit(e) {
      e.preventDefault();
      const { email = '', password = '' } = this.state.data;
      console.log(`email: ${email}, password: ${password}`);
      return false;
    }

    render() {
      const { password = '' } = this.state.data;

      return (
        <div style={{ width: '350px' }}>
          <Card className="px-6 py-6">
            <form onSubmit={this.onSubmit}>
              <Heading className="mb-7" size="m">Login</Heading>
              <Label withInput={true}>Email</Label>
              <Input
                name="input"
                type="text"
                placeholder="Enter email"
                className="mb-6"
                autocomplete={'off'}
                onChange={this.onEmailChange}
              />
              <Label withInput={true}>Password</Label>
              <Input
                name="input"
                className="mb-4"
                placeholder="Enter password"
                autocomplete={'off'}
                type={this.state.passwordVisible ? 'text' : 'password'}
                value={password}
                onChange={this.onPasswordChange}
                actionIcon={(
                  <Icon
                    name={this.state.passwordVisible ? 'visibility' : 'visibility_off'}
                    onClick={this.onActionClick}
                  />
                )}
              />
              <Link target="_blank" href="#">Forgot Password?</Link>
              <Button
                className="mt-7"
                appearance="primary"
                expanded={true}
                disabled={this.state.signInDisabled}
                type="submit"
              >
                Sign In
              </Button>
            </form>
          </Card>
        </div>
      );
    }
  }

  return <BasicForm />
}
```


#### Create Password Form

```jsx
import { Icon, Text, Card, Label, Input, Button } from '@innovaccer/design-system';



() => {
  const passwordRequirements = [
    { key: 'minLen',validation: 'At least eight (8) characters in length' },
    { key: 'uppercaseChar', validation: 'At least one (1) uppercase character'},
    { key: 'lowercaseChar', validation: 'At least one (1) lowercase character'},
    { key: 'numericChar', validation: 'At least one (1) numeric character' },
    { key: 'specialChar', validation: 'At least one (1) special character (! @ # $ \ _)'},
  ];

  const regex = {
    minLen: /^.{8,}$/,
    specialChar: /[!@#$%^&*()_+\-=\[\]{};':"\\|,.<>\/?]+/,
    lowercaseChar: /[a-z]/,
    uppercaseChar: /[A-Z]/,
    numericChar: /\d/
  };

  class CreatePassword extends React.Component {
    constructor(props = {}) {
      super(props);

      const validations = {
        minLen: false,
        uppercaseChar: false,
        lowercaseChar: false,
        numericChar: false,
        specialChar: false,
      };

      this.state = {
        validations,
        signInDisabled: true,
        password: '',
        confirmPassword: '',
        passwordVisible: false,
        confirmPasswordVisible: false,
      };

      this.onPasswordChange = this.onPasswordChange.bind(this);
      this.renderRequirements = this.renderRequirements.bind(this);
      this.onConfirmPasswordChange = this.onConfirmPasswordChange.bind(this);
      this.onSubmit = this.onSubmit.bind(this);
    }

    onPasswordChange(event) {
      const newPassword = event.target.value;

      const newValidations = Object.keys(this.state.validations).reduce((acc, curr) => {
        return { ...acc, [curr]: regex[curr].test(newPassword) }
      }, this.state.validations);

      const isValidated = Object.keys(newValidations).every(k => !newValidations[k]);
      const value=event.target.value;
      this.setState({
        password: value,
        validations: newValidations,
        signInDisabled: (!isValidated && value!== this.state.confirmPassword) || !value,
      });

    }

    onConfirmPasswordChange(event) {
      const value=event.target.value;
      this.setState({
        confirmPassword: value,
        signInDisabled: value !== this.state.password || !value
      });
    }

    renderRequirements() {

      return (
        <div>
          {
            passwordRequirements.map((item, index) => {
              const { validation, key } = item;

              return (
                <div className="d-flex mb-4 align-items-center" key={index}>
                  <Icon
                    className="mr-4"
                    name={this.state.validations[key] ? 'check_circle' : 'fiber_manual_record'}
                    appearance={this.state.validations[key] ? 'success' : 'default'}
                  />
                  <Text>{validation}</Text>
                </div>
              );
            })
          }
        </div>
      )
    }

    onSubmit(e) {
      e.preventDefault();
      console.log(this.state.password);
      return false;
    }

    render() {
      const { passwordVisible, confirmPasswordVisible } = this.state;

      return (
        <div style={{ width: '350px' }}>
          <Card className="px-6 py-6">
            <form onSubmit={this.onSubmit}>
              <Label withInput={true}>Password</Label>
              <Input
                name="input"
                className="mb-4"
                placeholder="Enter password"
                type={this.state.passwordVisible ? 'text' : 'password'}
                value={this.state.password}
                onChange={this.onPasswordChange}
                autocomplete="off"
                actionIcon={(
                  <Icon
                    name={this.state.passwordVisible ? 'visibility' : 'visibility_off'}
                    onClick={() => this.setState({ passwordVisible: !passwordVisible })}
                  />
                )}
              />
              {this.renderRequirements()}
              <Label withInput={true} className="mt-6">Confirm Password</Label>
              <Input
                name="input"
                placeholder="Enter password"
                type={this.state.confirmPasswordVisible ? 'text' : 'password'}
                value={this.state.confirmPassword}
                onChange={this.onConfirmPasswordChange}
                autocomplete="off"
                actionIcon={(
                  <Icon
                    name={this.state.confirmPasswordVisible ? 'visibility' : 'visibility_off'}
                    onClick={() => this.setState({ confirmPasswordVisible: !confirmPasswordVisible })}
                  />
                )}
              />
              <Button
                className="mt-7"
                appearance="primary"
                disabled={this.state.signInDisabled}
              >
                Next
            </Button>
            </form>
          </Card>
        </div>
      );
    }
  }

  return <CreatePassword />
}
```


#### Create User Form

```jsx
import { Card, Text, Row, Column, Label, Input, Dropdown, DatePicker, Button } from '@innovaccer/design-system';



() => {
  const genderOptions = [
    {
      label: 'Male',
      value: 'Male',
    },
    {
      label: 'Female',
      value: 'Female',
    }
  ];

  const userOptions = [
    {
      label: 'User A',
      value: 'UserA',
    },
    {
      label: 'User B',
      value: 'UserB',
    }
  ];

  class CreateUser extends React.Component {
    constructor(props = {}) {
      super(props);

      this.state = {
        updateDisabled: true,
        data: {},
      };

      this.onChange = this.onChange.bind(this);
      this.onSubmit = this.onSubmit.bind(this);
    }

    onChange(value, name) {
      const updatedData = { ...this.state.data, [name]: value };

      this.setState({
        data: updatedData,
        updateDisabled: Object.keys(updatedData).every(key => !updatedData[key])
      });
    }

    onSubmit(event) {
      event.preventDefault();
      console.log(this.state.data);
      return false;
    }

    render() {
      return (
      <div className="w-100">
        <Card className="px-6 py-6">
          <Text appearance="subtle" weight="strong">Primary Details</Text>
          <form onSubmit={this.onSubmit}>
            <Row className="mt-6">
              <Column sizeXL={4} sizeL={4} sizeM={6} className="mr-6 mb-6">
                <Label withInput={true} required={true}>Last Name</Label>
                <Input
                  name="lastName"
                  type="text"
                  placeholder="E.g. Doe, Smith, etc."
                  icon="person"
                  autocomplete={'off'}
                  onChange={(event) => this.onChange(event.target.value, event.target.name)}
                />
              </Column>
              <Column sizeXL={4} sizeL={4} sizeM={5} className="mr-6 mb-6">
                <Label withInput={true}>Middle Name</Label>
                <Input
                  name="middleName"
                  type="text"
                  placeholder="E.g. Doe, Smith, etc."
                  icon="person"
                  autocomplete={'off'}
                  onChange={(event) => this.onChange(event.target.value, event.target.name)}
                />
              </Column>
              <Column sizeXL={3} sizeL={3} sizeM={6} className="mr-6 mb-6">
                <Label withInput={true} required={true}>First Name</Label>
                <Input
                  name="firstName"
                  type="text"
                  placeholder="E.g. John, Will, etc."
                  icon="person"
                  autocomplete={'off'}
                  onChange={(event) => this.onChange(event.target.value, event.target.name)}
                />
              </Column>
              <Column sizeXL={4} sizeL={4} sizeM={5} className="mr-6 mb-6">
                <Label withInput={true}>Gender</Label>
                <Dropdown
                  options={genderOptions}
                  onChange={(value) => this.onChange(value, 'gender')}
                />
              </Column>
              <Column sizeXL={4} sizeL={4} sizeM={6} className="mr-6 mb-6">
                <Label withInput={true}>Date of Birth</Label>
                <DatePicker
                  withInput={true}
                  onDateChange={(currentDate) => this.onChange(currentDate, 'dob')}
                  inputOptions={{
                    placeholder: 'MM/DD/YYYY',
                    icon: 'cake',
                    mask: [/\d/, /\d/, '/', /\d/, /\d/, '/', /\d/, /\d/, /\d/, /\d/]
                  }}
                />
              </Column>
              <Column sizeXL={3} sizeL={3} sizeM={5} className="mr-6 mb-6">
                <Label withInput={true} >Maiden Name</Label>
                <Input
                  name="MaidenName"
                  type="text"
                  placeholder="E.g. Roe, Will, etc."
                  icon="person"
                  autocomplete={'off'}
                  onChange={(event) => this.onChange(event.target.value, event.target.name)}
                />
              </Column>
              <Column sizeXL={4} sizeL={4} sizeM={6} className="mr-6 mb-6">
                <Label withInput={true} required={true}>Email Address</Label>
                <Input
                  name="email"
                  type="email"
                  placeholder="E.g. abc@gmail.com"
                  autocomplete={'off'}
                  onChange={(event) => this.onChange(event.target.value, event.target.name)}
                />
              </Column>
              <Column sizeXL={4} sizeL={4} sizeM={5} className="mr-6 mb-6">
                <Label withInput={true}>User Type</Label>
                <Dropdown
                  options={userOptions}
                  placeholder="Select User Type"
                  onChange={(value) => this.onChange(value, 'userType')}
                />
              </Column>
              <Column sizeXL={3} sizeL={3} sizeM={5} className="mr-6 mb-6">
                <Label withInput={true} >NPI</Label>
                <Input
                  name="npi"
                  type="text"
                  placeholder="E.g. 000000"
                  autocomplete={'off'}
                  onChange={(event) => this.onChange(event.target.value, event.target.name)}
                />
              </Column>
            </Row>
            <div className="d-flex justify-content-end">
              <Button className="mr-4">Cancel</Button>
              <Button type="submit" appearance="success" disabled={this.state.updateDisabled}>Update Account</Button>
            </div>
          </form>
        </Card>
      </div>
      );
    }
  }

  return <CreateUser />
}
```


#### Inline Form

```jsx
import { Card, Label, Input, Button, DatePicker, Dropdown } from '@innovaccer/design-system';



() => {
  class InlineForm extends React.Component {

    constructor(props = {}) {
      super(props);

      this.state = {
        searchDisabled: true,
        data: {},
      };

      this.onChange = this.onChange.bind(this);
      this.onSubmit = this.onSubmit.bind(this);
    }

    onChange(value, name) {
      const updatedData = { ...this.state.data, [name]: value };

      this.setState({
        data: updatedData,
        searchDisabled: Object.keys(updatedData).every(key => !updatedData[key])
      });
    }

    onSubmit(e) {
      e.preventDefault();
      console.log(this.state.data);
      return false;
    }

    render() {
      const options = [];
      for (let i = 1; i <= 10; i++) {
        options.push({
          label: `Option ${i}`,
          value: `Option ${i}`,
        });
      }

      return (
        <div className="w-100">
          <Card className="px-6 py-6">
            <form onSubmit={this.onSubmit}>
              <div className="d-flex flex-wrap">
                <div className="mr-6 mb-6">
                  <Label withInput={true}>Last Name</Label>
                  <Input
                    name="lastName"
                    type="text"
                    placeholder="E.g. Doe, Smith, etc."
                    icon="person"
                    autocomplete={'off'}
                    onChange={(event) => this.onChange(event.target.value, event.target.name)}
                  />
                </div>
                <div className="mr-6 mb-6">
                  <Label withInput={true}>First Name</Label>
                  <Input
                    name="firstName"
                    type="text"
                    placeholder="E.g. John, Will, etc."
                    icon="person"
                    autocomplete={'off'}
                    onChange={(event) => this.onChange(event.target.value, event.target.name)}
                  />
                </div>
                <div className="mr-6 mb-6">
                  <Label withInput={true}>Gender</Label>
                  <div className="d-flex">
                    <Button className="mr-3" onClick={() => this.onChange('Male', 'gender')}>Male</Button>
                    <Button className="mr-3" onClick={() => this.onChange('Female', 'gender')}>Female</Button>
                    <Button className="mr-3" onClick={() => this.onChange('Other', 'gender')}>Other</Button>
                    <Button onClick={() => this.onChange('Unknown', 'gender')}>Unknown</Button>
                  </div>
                </div>
                <div className="mr-6 mb-6" style={{ width: 'var(--spacing-9)' }}>
                  <Label withInput={true}>Date of Birth</Label>
                  <DatePicker
                    withInput={true}
                    onDateChange={(currentDate) => this.onChange(currentDate, 'date')}
                    inputOptions={{
                      placeholder: 'MM/DD/YYYY',
                      icon: 'cake',
                      mask: [/\d/, /\d/, '/', /\d/, /\d/, '/', /\d/, /\d/, /\d/, /\d/]
                    }}
                  />
                </div>
                <div className="mr-6 mb-6">
                  <Label withInput={true}>EMPI</Label>
                  <Input
                    name="empi"
                    type="text"
                    placeholder="P000000"
                    icon="fingerprint"
                    autocomplete={'off'}
                    onChange={(event) => this.onChange(event.target.value, event.target.name)}
                  />
                </div>
                <div className="mr-6 mb-6">
                  <Label withInput={true}>MRN</Label>
                  <Input
                    name="mrn"
                    type="text"
                    placeholder="Medical Record Number"
                    icon="account_box"
                    autocomplete={'off'}
                    onChange={(event) => this.onChange(event.target.value, event.target.name)}
                  />
                </div>
                <div className="mr-6 mb-6">
                  <Label withInput={true}>ZIP</Label>
                  <Input
                    name="zip"
                    type="text"
                    placeholder="00000"
                    icon="location_on"
                    autocomplete={'off'}
                    onChange={(event) => this.onChange(event.target.value, event.target.name)}
                  />
                </div>
                <div className="mr-6 mb-6" style={{ width: 'var(--spacing-9)' }}>
                  <Label withInput={true}>Primary Care Physician</Label>
                  <Dropdown
                    icon="add_box"
                    placeholder="00000"
                    options={options}
                    onChange={(option) => this.onChange(option, 'pcp')}
                  />
                </div>
                <div className="mr-6 mb-6" style={{ width: 'var(--spacing-9)' }}>
                  <Label withInput={true}>Region</Label>
                  <Dropdown
                    icon="flag"
                    placeholder="00000"
                    options={options}
                    onChange={(option) => this.onChange(option, 'region')}
                  />
                </div>
              </div>
              <Button
                disabled={this.state.searchDisabled}
                appearance="primary"
                type="submit"
              >
                Search
              </Button>
            </form>
          </Card>
        </div>
      );
    }
  }

  return <InlineForm />
}
```


#### Inline Label Form

```jsx
import { Card, Row, Column, Icon, Text, Dropdown, Checkbox, Button, InputMask, Radio } from '@innovaccer/design-system';



() => {
  const languages = [
    {
      label: 'Hindi',
      value: 'Hindi',
    },
    {
      label: 'English',
      value: 'English',
      selected: true
    },
    {
      label: 'French',
      value: 'French',
    }
  ];

  class InlineLabelForm extends React.Component {
    constructor(props = {}) {
      super(props);

      this.state = {
        data: {
          language: 'English',
          defaultLanguage: 'English',
          defaultPhoneNumber: 'primaryPhoneNumber'
        },
      };

      this.onChange = this.onChange.bind(this);
      this.onSubmit = this.onSubmit.bind(this);
    }

    onChange(value, name) {
      const { defaultLanguage = '' } = this.state.data;

      const updatedData = {
        ...this.state.data,
        [name]: value,
      };

      this.setState({
        data: updatedData,
      });
    }

    onSubmit(event) {
      event.preventDefault();
      console.log(this.state.data);
      return false;
    }

    render() {
      const { defaultLanguage, language, defaultPhoneNumber } = this.state.data;

      return (
      <div className="w-100">
        <Card className="px-6 py-6">
          <form onSubmit={this.onSubmit}>
            <Row className="mb-6">
              <Column size={3} className="d-flex align-items-center">
                <Icon className="mr-4" name="language" />
                <Text>Known Languages</Text>
              </Column>
              <Column size={8} className="d-flex">
                <div className="mr-5 w-25">
                  <Dropdown
                    options={languages}
                    onChange={(value) => {
                      const updatedData = {
                        ...this.state.data,
                        language: value,
                        defaultLanguage: defaultLanguage !== '' ? value : defaultLanguage,
                      };
                      this.setState({data: updatedData})
                    }}
                  />
                </div>
                <Checkbox
                  name="defaultLanguage"
                  label="Set as Default"
                  defaultChecked={defaultLanguage}
                  onChange={(e) => {
                    const updatedData = {
                      ...this.state.data,
                      defaultLanguage: e.target.checked ? language : '',
                    };
                    this.setState({data: updatedData})
                  }}
                />
              </Column>
              <Column size={1} className="d-flex align-items-center justify-content-end">
                <Button icon="delete" appearance="transparent" />
              </Column>
            </Row>
            <Row className="my-5">
              <Column className="d-flex align-items-center" size={3}>
                <Icon className="mr-4" name="record_voice_over" />
                <Text>Preferred Method of Contact</Text>
              </Column>
              <Column size={8} className="d-flex">
                <Button className="mr-3" icon="call" onClick={() => this.onChange('phone', 'contact')}>Phone</Button>
                <Button className="mr-3" icon="chat" onClick={() => this.onChange('message', 'contact')}>Message</Button>
                <Button className="mr-3" icon="email" onClick={() => this.onChange('email', 'contact')}>Email</Button>
                <Button
                  className="mr-3"
                  icon="markunread_mailbox"
                  onClick={() => this.onChange('letter', 'contact')}
                >
                  Letter
                </Button>
              </Column>
              <Column size={1} className="d-flex align-items-center justify-content-end">
                <Button icon="delete" appearance="transparent" />
              </Column>
            </Row>
            <Row className="mt-6">
              <Column size={3} className="d-flex align-items-center">
                <Icon className="mr-4" name="call" />
                <Text>Phone Numbers</Text>
              </Column>
              <Column size={8} className="d-flex">
                <InputMask
                  mask={['(', /[1-9]/, /\d/, /\d/, ')', ' ', /\d/, /\d/, /\d/, '-', /\d/, /\d/, /\d/, /\d/]}
                  placeholder="(___) ___-____"
                  className="mr-4"
                  name="primaryPhoneNumber"
                  onChange={(e, value) => this.onChange(value, e.target.name)}
                />
                <Radio
                  defaultChecked={defaultPhoneNumber === 'primaryPhoneNumber'}
                  name="defaultPhoneNumber"
                  value="defaultPrimaryPhoneNumber"
                  label="Mark as Preferred"
                  onChange={(e) => {
                    const updatedData = {
                      ...this.state.data,
                      defaultPhoneNumber: e.target.checked ? 'primaryPhoneNumber' : defaultPhoneNumber
                    };
                    this.setState({data: updatedData})
                  }}
                />
              </Column>
              <Column size={1} className="d-flex align-items-center justify-content-end">
                <Button icon="delete" appearance="transparent" />
              </Column>
            </Row>
            <Row className="my-5">
              <Column size={3} className="d-flex align-items-center" />
              <Column size={8} className="d-flex">
                <InputMask
                  mask={['(', /[1-9]/, /\d/, /\d/, ')', ' ', /\d/, /\d/, /\d/, '-', /\d/, /\d/, /\d/, /\d/]}
                  placeholder="(___) ___-____"
                  className="mr-4"
                  name="secondaryPhoneNumber"
                  onChange={(e, value) => this.onChange(value, e.target.name)}
                />
                <Radio
                  defaultChecked={defaultPhoneNumber === 'secondaryPhoneNumber'}
                  name="defaultPhoneNumber"
                  value="defaultSecondaryPhoneNumber"
                  label="Mark as Preferred"
                  onChange={(e) => {
                    const updatedData = {
                      ...this.state.data,
                      defaultPhoneNumber: e.target.checked ? 'secondaryPhoneNumber' : defaultPhoneNumber
                    };
                    this.setState({data: updatedData})
                  }}
                />
              </Column>
              <Column size={1} className="d-flex align-items-center justify-content-end">
                <Icon name="flag" appearance="warning" className="mr-4"/>
              </Column>
            </Row>
          <div className="d-flex">
            <Button className="mr-4" type="submit" appearance="success">Save</Button>
            <Button>Cancel</Button>
          </div>
          </form>
        </Card>
      </div>
      );
    }
  }

  return <InlineLabelForm />
}
```


#### Stepper Form

```jsx
import { Button, Card, Stepper, Text, Badge, Dropdown, Label, InputMask, Avatar, Textarea, Switch } from '@innovaccer/design-system';



() => {
  const steps = [
    {
      label: 'Define Input/Output',
      value: 'Define_Input_Output'
    },
    {
      label: 'Add Configuration',
      value: 'Add_Configuration'
    },
  ];
  const totalSteps = steps.length;

  const options = [];
  for (let i = 1; i <= 10; i++) {
    options.push({
      label: `Option ${i}`,
      value: `Option ${i}`,
    });
  }

  class StepperForm extends React.Component {
    constructor(props = {}) {
      super(props);

      this.state = {
        activeStep: 0,
        completedStep: -1,
        data: {},
        configuration: {},
      };

      this.onChangeStep = this.onChangeStep.bind(this);
      this.onClickNext = this.onClickNext.bind(this);
      this.onChangeOutput = this.onChangeOutput.bind(this);
      this.onSubmit = this.onSubmit.bind(this);
      this.renderButton = this.renderButton.bind(this);
    }

    onChangeStep(activeStep) {
      this.setState({
        activeStep
      })
    }

    onChangeOutput(value, name) {
      const data = {
        ...this.state.data,
        [name]: value,
      };

      this.setState({
        data
      });
    }

    onClickNext() {
      const { activeStep, completedStep } = this.state;
      const updatedActive = activeStep > completedStep ? activeStep + 1 : completedStep + 1;
      this.setState({
        activeStep: updatedActive,
        completedStep: activeStep > completedStep ? activeStep : completedStep
      });
    }

    onSubmit(event) {
      event.preventDefault();
      console.log(this.state.data);
      console.log(this.state.configuration);
      return false;
    }

    renderButton() {
      if (this.state.activeStep + 1 === totalSteps) {
        return <Button appearance="success" type="submit">Save</Button>
      }

      return <Button appearance="primary" onClick={this.onClickNext}>Next</Button>
    }

    render() {
      const { value } = steps[this.state.activeStep];

      return (
        <div className="w-75">
          <Card className="px-7 py-6">
            <form onSubmit={this.onSubmit}>
              <div className="d-flex justify-content-between">
                <Stepper
                  steps={steps}
                  active={this.state.activeStep}
                  completed={this.state.completedStep}
                  onChange={this.onChangeStep}
                />
                {this.renderButton()}
              </div>
              <div className={value !== 'Define_Input_Output' ? 'd-none' : ''}>
                <div className="d-flex mr-3 mt-7 mb-2">
                  <Text weight="strong" className="mr-4">Source</Text>
                  <Badge appearance="warning">2 Inputs</Badge>
                </div>
                <Text size="small" appearance="subtle">
                  The system automatically creates collection for multiple support.
                </Text>
                <div className="w-50 mt-4">
                  <Dropdown
                    options={options}
                    placeholder="Input Collection 1"
                    className="mb-4"
                    onChange={(value) => this.onChangeOutput(value, 'collection1')}
                  />
                  <Dropdown
                    options={options}
                    placeholder="Input Collection 2"
                    onChange={(value) => this.onChangeOutput(value, 'collection2')}
                  />
                </div>
                <div className="d-flex mr-3 mt-8 mb-2">
                  <Text weight="strong" className="mr-4">Destination</Text>
                  <Badge appearance="success">8 Outputs</Badge>
                </div>
                <Text size="small" appearance="subtle">
                  The system automatically creates collection for multiple support.
                </Text>
                <div className="w-50 mt-6">
                  <Label withInput={true}>Destination Collection</Label>
                  <Dropdown
                    options={options}
                    placeholder="Select Destination"
                    onChange={(value) => this.onChangeOutput(value, 'collection')}
                  />
                </div>
                <div className="mt-6 w-50">
                  <Label withInput={true} required>Prefix</Label>
                  <InputMask
                    mask={[/\d/, '_', /\d/, '_', /\d/]}
                    name="prefix"
                    placeholder="<workspace_id>_<workflow_id>_<pipeline_id>"
                    placeholderChar="-"
                    onChange={(e) => this.onChangeOutput(e.target.value, e.target.name)}
                  />
                </div>
                <div className="w-25 mt-6">
                  <Label withInput={true} required>Retention</Label>
                  <Dropdown options={options} onChange={(value) => this.onChangeOutput(value, 'retention')} />
                  <Label className="mt-6" withInput={true}>Visibility Clarification</Label>
                  <Dropdown options={options} onChange={(value) => this.onChangeOutput(value, 'clarification')} />
                </div>
              </div>
              <div className={value !== 'Add_Configuration' ? 'd-none' : ''}>
                <div className="d-flex mt-7">
                  <Avatar className="mr-5" firstName="A" appearance="success" />
                  <div className="d-flex flex-column">
                    <Text weight="strong" className="mb-2">Job Configuration</Text>
                    <Text size="small" appearance="subtle">
                      The system automatically creates collection for multiple support.
                    </Text>
                  </div>
                </div>
                <div className="w-25 mt-6">
                  <Label withInput={true} required>Mode</Label>
                  <Dropdown
                    options={options}
                    onChange={(value) => {
                      this.setState({
                        configuration: { ...this.state.configuration, mode: value }
                      });
                    }}
                  />
                </div>
                <div className="mt-6 w-50">
                  <Label withInput={true} required>Regex</Label>
                  <Textarea
                    rows={3}
                    onChange={(e, value) => {
                      this.setState({
                        configuration: { ...this.state.configuration, regex: value }
                      });
                    }}
                  />
                </div>
                <Label className="mt-6" withInput={true} required>Retention</Label>
                <Switch appearance="primary" defaultChecked={true} className="d-flex" />
              </div>
            </form>
          </Card>
        </div>
      );
    }

  }

  return <StepperForm />
}
```


#### Time Period Form

```jsx
import { Card, Heading, Text, Label, Dropdown, Link, DateRangePicker, Slider, Paragraph, Button } from '@innovaccer/design-system';



() => {
  class TimePeriodForm extends React.Component {
    constructor(props = {}) {
      super(props);

      this.state = {
        time: 8,
        budget: 60
      };
    }

    render() {
      const options = [];
      for (let i = 1; i <= 10; i++) {
        options.push({
          label: `Option ${i}`,
          value: `Option ${i}`,
        });
      }

      return (
        <div className="w-75">
          <Card className="px-7 py-6">
            <Heading className="mb-6" size="s">Configure Initiative</Heading>
            <Text weight="strong">Population Filter</Text>
            <div className="d-flex mt-5 mb-4">
              <div className="mr-6" style={{ width: 'var(--spacing-8)' }}>
                <Label withInput={true}>Region</Label>
                <Dropdown options={options} />
              </div>
              <div style={{ width: 'var(--spacing-9)' }}>
                <Label withInput={true}>Organization</Label>
                <Dropdown options={options} />
              </div>
            </div>
            <Link target="_blank" href="#">Add organizations</Link>
            <div className="my-6 pt-6" style={{ borderTop: 'var(--spacing-xs) solid var(--secondary-light)' }}>
              <Text weight="strong">Time Period</Text>
              <div className="mt-5">
                <DateRangePicker withInput />
              </div>
              <Slider
                className="mt-6 mb-7"
                label="Care Manager - Time Allocation"
                min={1}
                max={10}
                stepSize={1}
                value={this.state.time}
                onChange={(value) => this.setState({ time: value })}
                labelRenderer={(value) => this.state.time === value ? `${value}` : ''}
              />
              <Paragraph appearance="subtle">Limit to <b>{this.state.time} hours</b> per day per Care Manager</Paragraph>
              <Slider
                className="mt-6 mb-7"
                label="Budget Allocation"
                min={10}
                max={100}
                stepSize={10}
                labelStepSize={10}
                value={this.state.budget}
                onChange={(value) => this.setState({ budget: value })}
                labelRenderer={(value) => this.state.budget === value ? `$${value}K` : ''}
              />
              <Paragraph appearance="subtle">Allocated Budget: <b>${this.state.budget}K</b> </Paragraph>
            </div>
            <div
              className="mt-7 pt-5 d-flex justify-content-end"
              style={{ borderTop: 'var(--spacing-xs) solid var(--secondary-light)' }}
            >
              <Button appearance="basic" className="mr-4">Cancel</Button>
              <Button appearance="success">Initiate</Button>
            </div>
          </Card>
        </div>
      );
    }
  }

  return <TimePeriodForm />
}
```


#### Verification Code Input

```jsx
import { Text, Message, Card, Label, VerificationCodeInput, Spinner } from '@innovaccer/design-system';

() => {
  class VerificationCodeInputCard extends React.Component {
    constructor(props) {
      super(props);

      this.correctValue = '555123';
      this.state = {
        isTimerStarted: false,
        timer: 30,
        loading: false,
        value: '',
        error: false,
      };

      this.onToogleLink = this.onToogleLink.bind(this);
      this.onCompleteHandler = this.onCompleteHandler.bind(this);
    }

    componentDidUpdate(prevProps, prevState) {
      const { timer, isTimerStarted } = this.state;

      if (isTimerStarted
        && (timer !== prevState.time || prevState.isTimerStarted !== isTimerStarted)
      ) {
        if (timer > 0) {
          setTimeout(() => {
            this.setState({
              timer: timer - 1,
            })
          }, 1000);
        }

        if (timer === 0) {
          this.setState({
            isTimerStarted: !isTimerStarted,
          });
        }
      }
    }

    onToogleLink() {
      if (this.state.loading || !!this.state.value) return;
      this.setState({
        isTimerStarted: true,
        timer: 30
      });
    };

    onCompleteHandler(value) {
      this.setState({
        loading: true,
        timer: 0,
        isTimerStarted: false,
      });

      setTimeout(() => {
        this.setState({
          value: value === this.correctValue ? value : '',
          loading: false,
          error: value !== this.correctValue
        });
      }, 2000);
    };

    render() {
      const { isTimerStarted, timer, loading, value, error } = this.state;
      const time = timer < 10 ? `0${timer}` : timer;

      return (
        <div>
          <div className="mb-5">
            <Text weight="strong">Note: </Text>
            <Text weight="medium">{`Verified value of Verification Code Input is ${this.correctValue} in this example.`}</Text>
          </div>
          <div className="w-50">
            {(value || error) && (
              <Message
                appearance={error ? 'alert' : 'success'}
                description={error? 'The code that you have entered is invalid or incorrect. Try again.' : 'Verification Successful.'}
                className="mb-5"
              />
            )}
            <Card className="py-6 px-6">
              <div className="d-flex flex-column">
                <Text weight="strong" size="large">Enter Verification Code</Text>
                <Text className="mt-3" appearance="subtle">
                  We have sent a 6 digit verification code to your phone (555) 555-1234
                </Text>
              </div>
              <Label withInput={true} className="mt-7">Verification code</Label>
              <div className="d-flex align-items-center">
                <VerificationCodeInput
                  fields={6}
                  onComplete={this.onCompleteHandler}
                  disabled={loading || !!value}
                />
                {loading && <Spinner className="ml-5" size="medium" />}
              </div>
              {isTimerStarted ? (
                <Text className="mt-7 d-flex" weight="medium">
                  {`Haven't recieved the code? Resend code in 0:${time}`}
                </Text>
              ) : (
                  <Text
                    className="mt-7 d-flex cursor-pointer"
                    appearance={loading || !!value ? 'disabled' : 'link'}
                    weight="medium"
                    onClick={this.onToogleLink}
                  >
                    Resend Code
                  </Text>
                )}
            </Card>
          </div>
        </div>
      );
    }
  };

  return <><VerificationCodeInputCard /></>
}
```


#### Blank Template

```jsx
import { Row, Column } from '@innovaccer/design-system';

() => {
  return(
    <Row className="d-flex flex-column bg-secondary-lightest vh-100 p-6">
      <Column>
        <div className="h-100 bg-light" />
      </Column>
    </Row>
  );
}
```


#### Level 1 Header Template

```jsx
import { Navigation, Button, Breadcrumbs, Badge, PageHeader, Row, Column } from '@innovaccer/design-system';

() => {
  const navigationPosition = 'center';
  const title = 'Page title';
  const navigationData = [
    {
      name: 'menu_1',
      label: 'Menu 1',
      icon: 'event',
    },
    {
      name: 'menu_2',
      label: 'Menu 2'
    },
    {
      name: 'menu_3',
      label: 'Menu 3',
      disabled: true
    }
  ];
  const breadcrumbData = [
    {
      label: 'Level 0',
      link: '/level0'
    },
    {
      label: 'Level 1',
      link: '/level1'
    }
  ];

  const options = {
    navigationPosition,
    title,
    navigation: <Navigation menus={navigationData} onClick={menu => console.log(menu)} active={{ name: 'menu_1' }} />,
    actions: (
      <div style={{ display: 'flex', justifyContent: 'flex-end', alignItems: 'center' }}>
        <Button appearance="primary">Primary</Button>
      </div>
    ),
    breadcrumbs: (
      <Breadcrumbs
        list={breadcrumbData}
        onClick={link => console.log(link)}
      />
    ),
    badge: (
      <Badge appearance="secondary">Badge</Badge>
    )
  };

  return(
    <div className="d-flex flex-column bg-secondary-lightest vh-100">
      <PageHeader
        {...options}
      />
      <Row className="h-100 p-6">
        <Column className="h-100 bg-light" />
      </Row>
    </div>
  );
}
```


#### Mini sidebar Template

```jsx
import { Row, Collapsible, VerticalNav, Column, PageHeader, Icon, Heading } from '@innovaccer/design-system';

() => {
  const menus = [
    {
      name: 'patient_360',
      label: 'Patient 360',
      icon: 'assignment_ind',
      link: '/patient360',
    },
    {
      name: 'care_management',
      label: 'Care Management and Resources',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      disabled: true,
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite',
      subMenu: [
        {
          name: 'risk.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'risk.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'receipt'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'account_circle'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    }
  ];

  const [expanded, setExpanded] = React.useState(false);
  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return(
    <Row className="vh-100 bg-secondary-lightest">
        <Collapsible expanded={expanded} onToggle={setExpanded}>
          <VerticalNav
            menus={menus}
            expanded={expanded}
            active={active}
            onClick={onClickHandler}
            hoverable={false}
          />
        </Collapsible>
      <Column
        className="d-flex flex-column pb-6"
      >
        <PageHeader title="Page title" separator={false} />
        <Row className="px-6 h-100">
          <Column className="h-100 bg-light" />
        </Row>
      </Column>
      <Column size={'auto'}>
        <div className="d-flex flex-column py-4">
          <Icon name="assignment_ind" className="m-4"/>
          <Icon name="account_circle" className="m-4"/>
        </div>
      </Column>
      <Column
        size={3}
        className="d-flex flex-column pb-6"
      >
        <Heading className='px-6 py-4'>Page Title</Heading>
        <Row className="px-6 h-100">
          <Column className="h-100 bg-light" />
        </Row>
      </Column>
    </Row>
  );
}
```


#### Narrow width content Template

```jsx
import { Row, Collapsible, VerticalNav, Column, PageHeader } from '@innovaccer/design-system';

() => {
  const menus = [
    {
      name: 'patient_360',
      label: 'Patient 360',
      icon: 'assignment_ind',
      link: '/patient360',
    },
    {
      name: 'care_management',
      label: 'Care Management and Resources',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      disabled: true,
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite',
      subMenu: [
        {
          name: 'risk.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'risk.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'receipt'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'account_circle'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    }
  ];

  const [expanded, setExpanded] = React.useState(false);
  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return(
    <Row className="vh-100 bg-secondary-lightest flex-nowrap">
      <Collapsible expanded={expanded} onToggle={setExpanded}>
        <VerticalNav
          menus={menus}
          expanded={expanded}
          active={active}
          onClick={onClickHandler}
          hoverable={false}
        />
      </Collapsible>
      <Row className="justify-content-center">
        <Column size={8} className="d-flex flex-column pb-6">
          <PageHeader
            title="Page title"
            separator={false}
          />
          <Row className="px-6 h-100">
            <Column className="h-100 bg-light" />
          </Row>
        </Column>
      </Row>
    </Row>
  );
}
```


#### Resource Table Template

```jsx
import { PageHeader, Row, Column } from '@innovaccer/design-system';

() => {
  return(
    <div className="d-flex flex-column bg-secondary-lightest vh-100 pb-6">
      <PageHeader
        title="Page title"
        separator={false}
      />
      <Row className="px-6 h-100">
        <Column className="h-100 bg-light" />
      </Row>
    </div>
  );
}
```


#### Sidebar Template

```jsx
import { Row, Collapsible, VerticalNav, Column, PageHeader } from '@innovaccer/design-system';

() => {
  const menus = [
    {
      name: 'patient_360',
      label: 'Patient 360',
      icon: 'assignment_ind',
      link: '/patient360',
    },
    {
      name: 'care_management',
      label: 'Care Management and Resources',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      disabled: true,
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite',
      subMenu: [
        {
          name: 'risk.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'risk.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'receipt'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'account_circle'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    }
  ];

  const [expanded, setExpanded] = React.useState(false);
  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return(
    <Row className="vh-100 bg-secondary-lightest">
      <Collapsible expanded={expanded} onToggle={setExpanded}>
        <VerticalNav
          menus={menus}
          expanded={expanded}
          active={active}
          onClick={onClickHandler}
          hoverable={false}
        />
      </Collapsible>
      <Column className="d-flex flex-column pb-6">
        <PageHeader
          title="Page title"
          separator={false}
        />
        <Row className="px-6">
          <Column className="h-100 bg-light" />
        </Row>
      </Column>
    </Row>
  );
}
```


#### Async Table With Filters

```jsx
import {  } from '@innovaccer/design-system';

() => <></>
```


#### Sync Table With Filters

```jsx
import {  } from '@innovaccer/design-system';

() => <></>
```


#### Table with header

```jsx
import { Popover, Button, Checkbox, Icon, Input, Dropdown, Placeholder, PlaceholderParagraph, Label, Card, Grid, Pagination, Subheading, DatePicker, Table } from '@innovaccer/design-system';

/*
import * as React from 'react';
import { debounce } from 'throttle-debounce';
import {
  Card,
  Button,
  Label,
  Grid,
  Placeholder,
  PlaceholderParagraph,
  Dropdown,
  Input,
  Checkbox,
  Subheading,
  Icon,
  Pagination,
  DatePicker,
} from '@innovaccer/design-system';
import './style.css';

// styles.css
.Table-container {
  display: flex;
  height: 100%;
}

.Table-filters {
  box-sizing: border-box;
  display: flex;
  flex-shrink: 0;
}

.Table-filters--vertical {
  flex-direction: column;
  height: 100%;
  width: var(--spacing-9);
  padding: 0 var(--spacing-l);
}

.Table-filtersHeading {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.Table-filtersCloseIcon {
  cursor: pointer;
}

.Table-filters--vertical .Table-filter {
  padding: var(--spacing) 0;
}

.Table-filters--vertical .Table-filter:first-of-type {
  padding-top: var(--spacing-l);
}

.Table-filters--vertical .Table-filter:last-of-type {
  padding-bottom: var(--spacing-l);
}

.Table-filters--horizontal .Table-filter {
  padding: 0 var(--spacing-m);
}

.Table-filters--horizontal .Table-filter:first-of-type {
  padding-left: 0;
}

.Table-filters--horizontal .Table-filter:last-of-type {
  padding-right: 0;
}

.Table-filter .Input {
  min-width: unset;
}
*/

() => {
  const getSelectAll = (data) => {
    if (data.length) {
      const anyUnSelected = data.some(d => !d._selected);
      const allUnSelected = data.every(d => !d._selected);
  
      const indeterminate = data.length >= 0 && anyUnSelected && !allUnSelected;
      const checked = !indeterminate && !allUnSelected;
  
      return { indeterminate, checked };
    }
    return { indeterminate: false, checked: false };
  };
  
  const getTotalPages = (totalRecords, pageSize) => Math.ceil(totalRecords / pageSize);
  
  const hasSchema = schema => (schema && !!schema.length);

  const getPluralSuffix = (count) => count > 1 ? 's' : '';
  
  const updateBatchData = (data, rowIndexes, dataUpdate) => {
    const updatedData = [...data];
    for (const rowIndex of rowIndexes) {
      updatedData[rowIndex] = {
        ...updatedData[rowIndex],
        ...dataUpdate
      };
    }
  
    return updatedData;
  };

  const moveToIndex = (arr, from, to) => {
    if (from === to) return arr;
  
    let newArr = arr;
    if (from < to) {
      newArr = [
        ...arr.slice(0, from),
        ...arr.slice(from + 1, to + 1),
        arr[from],
        ...arr.slice(to + 1)
      ];
    } else {
      newArr = [
        ...arr.slice(0, to),
        arr[from],
        ...arr.slice(to, from),
        ...arr.slice(from + 1)
      ];
    }
  
    return newArr;
  };

  const DraggableDropdown = (props) => {
    const {
      options,
      onChange
    } = props;
  
    const [open, setOpen] = React.useState(false);
    const [tempOptions, setTempOptions] = React.useState(options);
    const [triggerWidth, setTriggerWidth] = React.useState('var(--spacing-8)');
  
    React.useEffect(() => {
      setTempOptions(options);
    }, [open]);
  
    const handleParentChange = (e) => {
      setTempOptions(tempOptions.map(option => ({ ...option, selected: e.target.checked })));
    };
  
    const handleChildChange = (e, index) => {
      const newOptions = [...tempOptions];
      newOptions[index] = {
        ...newOptions[index],
        selected: e.target.checked
      };
  
      setTempOptions(newOptions);
    };
  
    const onToggleHandler = (newOpen) => {
      setOpen(newOpen);
    };
  
    const onCancelHandler = () => {
      setOpen(false);
    };
  
    const onApplyHandler = () => {
      setOpen(false);
  
      if (onChange) onChange(tempOptions);
    };
  
    return (
      <div className="Dropdown">
        <Popover
          open={open}
          onToggle={onToggleHandler}
          trigger={(
            <Button
              ref={el => {
                // setTriggerWidth(`${el.clientWidth}px`);
              }}
              size="tiny"
              appearance="transparent"
              icon="keyboard_arrow_down_filled"
              iconAlign="right"
            >
              {`Showing ${options.filter(option => option.selected).length} of ${options.length} column${getPluralSuffix(options.length)}`}
            </Button>
          )}
          triggerClass="w-100"
          customStyle={{
            width: triggerWidth
          }}
          className="Header-draggableDropdown"
        >
          <div className="Dropdown-wrapper">
            <div className="OptionWrapper">
              <Checkbox
                className="OptionCheckbox"
                label="Select All"
                checked={tempOptions.every(option => option.selected)}
                indeterminate={tempOptions.some(option => option.selected)
                  && tempOptions.some(option => !option.selected)}
                onChange={handleParentChange}
              />
            </div>
            {tempOptions.map((option, index) => {
              return (
                <div
                  key={option.value}
                  className="OptionWrapper d-flex flex-space-between align-items-center cursor-pointer"
                  draggable={true}
                  onDragStart={e => {
                    e.dataTransfer.setData('index', `${index}`);
                  }}
                  onDragOver={e => e.preventDefault()}
                  onDrop={e => {
                    const from = +e.dataTransfer.getData('index');
                    const to = index;
  
                    if (from !== to) setTempOptions(moveToIndex(tempOptions, from, to));
                  }}
                >
                  <Checkbox
                    className="OptionCheckbox"
                    name={option.value}
                    label={option.label}
                    checked={tempOptions[index].selected}
                    onChange={e => handleChildChange(e, index)}
                  />
                  <Icon name="drag_handle" className="mr-4" />
                </div>
              );
            })}
          </div>
          <div className="Dropdown-buttonWrapper">
            <Button className="mr-4" size="tiny" onClick={onCancelHandler}>Cancel</Button>
            <Button appearance="primary" size="tiny" onClick={onApplyHandler}>Apply</Button>
          </div>
        </Popover>
      </div>
    );
  };
  
  const Header = (props) => {
    const {
      loading,
      error,
      data,
      schema,
      showHead,
      withPagination,
      page,
      pageSize,
      withCheckbox,
      updateSchema,
      filterList = {},
      updateFilterList,
      totalRecords = 0,
      onSelectAll,
      searchPlaceholder,
      selectAll,
      searchTerm,
      updateSearchTerm,
      allowSelectAll,
      updateShowVerticalFilters
    } = props;
  
    const [selectAllRecords, setSelectAllRecords] = React.useState(false);
    const [flag, setFlag] = React.useState(true);
  
    React.useEffect(() => {
      setFlag(!flag);
    }, [schema]);
  
    React.useEffect(() => {
      if (selectAll && selectAll.checked) {
        if (onSelectAll) onSelectAll(true, selectAllRecords);
      }
    }, [selectAllRecords]);
  
    React.useEffect(() => {
      if (selectAll && !selectAll.checked) setSelectAllRecords(false);
    }, [selectAll]);
  
    const filterSchema = schema.filter(s => s.filters);
  
    const onSearchChange = e => {
      const value = e.target.value;
      if (updateSearchTerm) {
        updateSearchTerm(value);
      }
    };
  
    const onFilterChange = (name, filters) => {
      const newFilterList = {
        ...filterList,
        [name]: filters
      };
  
      if (updateFilterList) {
        updateFilterList(newFilterList);
      }
    };
  
    const columnOptions = schema.map(s => ({
      label: s.displayName,
      value: s.name,
      selected: !s.hidden
    }));
  
    const onDynamicColumnUpdate = (options) => {
      const newSchema = options.map(option => ({
        ...schema.find(colSchema => colSchema.name === option.value),
        hidden: !option.selected
      }));
  
      if (updateSchema) updateSchema(newSchema);
    };
  
    const selectedCount = data.filter(d => d._selected).length;
    const startIndex = (page - 1) * pageSize + 1;
  const endIndex = Math.min(page * pageSize, totalRecords);
  const label = error
    ? `Showing 0 items`
    : withCheckbox && selectedCount
      ? selectAllRecords
        ? `Selected all ${totalRecords} item${getPluralSuffix(totalRecords)}`
        : `Selected ${selectedCount} item${getPluralSuffix(totalRecords)} on this page`
      : withPagination
        ? `Showing ${startIndex}-${endIndex} of ${totalRecords} item${getPluralSuffix(totalRecords)}`
        : `Showing ${totalRecords} item${getPluralSuffix(totalRecords)}`;
  
    return (
      <div className="Header">
        <div className="Header-content Header-content--top">
          <div className="Header-search">
            <Input
              name="GridHeader-search"
              icon="search"
              placeholder={searchPlaceholder}
              onChange={onSearchChange}
              value={searchTerm}
              onClear={() => updateSearchTerm && updateSearchTerm('')}
              disabled={loading && !hasSchema(schema)}
            />
          </div>
          <div className="Header-dropdown">
            <div className="Table-filters Table-filters--horizontal">
              <div className="Table-filter">
                <Dropdown
                  key="name"
                  disabled={loading}
                  withCheckbox={true}
                  showApplyButton={true}
                  inlineLabel={"Name"}
                  options={[
                    { label: 'A-G', value: 'a-g', selected: true },
                    { label: 'H-R', value: 'h-r', selected: true },
                    { label: 'S-Z', value: 's-z', selected: true },
                  ]}
                  onChange={selected => onFilterChange("name", selected)}
                />
              </div>
              <div className="Table-filter">
                <Button
                  icon="add"
                  onClick={() => updateShowVerticalFilters(true)}
                >
                  More Filters
                </Button>
              </div>
            </div>
          </div>
          <div className="Header-actions">
          </div>
        </div>
        <div className="Header-content Header-content--bottom">
          <div className="Header-label">
            {showHead && !loading && (
              <Checkbox
                {...selectAll}
                onChange={event => {
                  if (onSelectAll) onSelectAll(event.target.checked);
                }}
              />
            )}
            {loading ? (
              <Placeholder withImage={!showHead && withCheckbox}>
                <PlaceholderParagraph length={'small'} size={'s'} />
              </Placeholder>
            ) : (
                <>
                  <Label>{label}</Label>
                  {withPagination && selectAll.checked && allowSelectAll && (
                    <div className="ml-4">
                      {!selectAllRecords ? (
                        <Button
                          size="tiny"
                          onClick={() => setSelectAllRecords(true)}
                        >
                          {`Select all 	otalRecords} items`}
                        </Button>
                      ) : (
                          <Button
                            size="tiny"
                            onClick={() => setSelectAllRecords(false)}
                          >
                            Clear selection
                          </Button>
                        )
                      }
                    </div>
                  )}
                </>
              )
            }
          </div>
          <div className="Header-hideColumns">
            <DraggableDropdown
              options={columnOptions}
              onChange={onDynamicColumnUpdate}
            />
          </div>
        </div>
      </div>
    );
  };
  
  Header.defaultProps = {
    schema: [],
    data: [],
    searchPlaceholder: 'Search',
    dynamicColumn: true
  };
  
  class Table extends React.Component {
    constructor(props) {
      super(props);
  
      this.state = {
        data: [],
        schema: [],
        page: 1,
        totalRecords: 0,
        sortingList: props.sortingList || [],
        filterList: props.filterList || {},
        loading: true,
        error: false,
        selectAll: getSelectAll([]),
        searchTerm: undefined,
        showVerticalFilters: props.showVerticalFilters,
      };
  
      this.pageSize = 4;
      this.searchDebounceDuration = 750;
      this.debounceUpdate = debounce(this.searchDebounceDuration, this.updateDataFn);
    }

    componentDidMount() {
      this.updateData();
    }
  
    componentDidUpdate(_prevProps, prevState) {
      if (prevState.page !== this.state.page) {
        const { onPageChange } = this.props;
        if (onPageChange) onPageChange(this.state.page);
      }
  
      if (prevState.page !== this.state.page
        || prevState.filterList !== this.state.filterList
        || prevState.sortingList !== this.state.sortingList
        || prevState.searchTerm !== this.state.searchTerm) {
        if (!this.props.loading) this.updateData({});
      }
    }

    updateData() {
      this.setState({
        loading: true
      });
  
      this.debounceUpdate();
    }
  
    updateDataFn() {
      this.onSelect(-1, false);
  
      const {
        fetchData,
      } = this.props;
  
      const {
        page,
        sortingList,
        filterList,
        searchTerm
      } = this.state;
  
      const {
        pageSize
      } = this;
  
      const opts = {
        page,
        pageSize,
        sortingList,
        filterList,
        searchTerm,
      };
  
      this.setState({
        loading: true
      });
      if (fetchData) {
        fetchData(opts)
          .then((res) => {
            const data = res.data;
            const schema = this.state.schema.length ? this.state.schema : res.schema;
            this.setState({
              data,
              schema,
              selectAll: getSelectAll(data),
              totalRecords: res.count,
              loading: false,
              error: !data.length
            });
          })
          .catch(() => {
            this.setState({
              loading: false,
              error: true,
              data: []
            });
          });
      }
    }
  
    onSelect(rowIndexes, selected) {
      const {
        data
      } = this.state;
  
      const {
        onSelect
      } = this.props;
  
      const indexes = [rowIndexes];
      let newData = data;
      if (rowIndexes >= 0) {
        newData = updateBatchData(data, indexes, {
          _selected: selected
        });
  
        this.setState({
          data: newData,
          selectAll: getSelectAll(newData)
        });
      }
  
      if (onSelect) {
        onSelect(indexes, selected, rowIndexes === -1 ? [] : newData.filter(d => d._selected));
      }
    }
  
    onSelectAll(selected, selectAll) {
      const {
        onSelect
      } = this.props;
  
      const {
        data
      } = this.state;
  
      const indexes = Array.from({ length: data.length }, (_, i) => i);
  
      const newData = updateBatchData(data, indexes, {
        _selected: selected
      });
  
      if (onSelect) {
        onSelect(indexes, selected, newData.filter(d => d._selected), selectAll);
      }
  
      this.setState({
        data: newData,
        selectAll: getSelectAll(newData)
      });
    }
  
    onPageChange(newPage) {
      this.setState({
        page: newPage
      });
    }
  
    onFilterChange(name, selected) {
      const {
        filterList
      } = this.props;
  
      const newFilterList = {
        ...filterList,
        [name]: selected
      };
  
      this.updateFilterList(newFilterList);
    }
  
    updateShowVerticalFilters(val) {
      this.setState({
        showVerticalFilters: val
      });
    }
  
    updateSchema(newSchema) {
      this.setState({
        schema: newSchema
      });
    }
  
    updateSortingList(newSortingList) {
      const {
        multipleSorting
      } = this.props;
  
      this.setState({
        sortingList: multipleSorting ? [...newSortingList] : newSortingList.slice(-1),
        page: 1,
      });
    }
  
    updateFilterList(newFilterList) {
      this.setState({
        filterList: newFilterList,
        page: 1,
      });
    }
  
    updateSearchTerm(newSearchTerm) {
      this.setState({
        searchTerm: newSearchTerm,
        page: 1
      });
    }
  
    render() {
      const {
        loaderSchema,
      } = this.props;
  
      const withCheckbox = true;
      const withPagination = true;
      const {
        pageSize
      } = this;
  
      const {
        totalRecords,
        showVerticalFilters,
        loading
      } = this.state;
      const totalPages = getTotalPages(totalRecords, pageSize);

      const classNames = showVerticalFilters ? 'Table-verticalFilter' : 'w-100';

      return (
        <div className="Table-container">
          <div className={classNames}>
            <Card className="Table overflow-hidden">
              <div className="Table-header">
                <Header
                  {...this.state}
                  updateSchema={this.updateSchema.bind(this)}
                  updateFilterList={this.updateFilterList.bind(this)}
                  updateSearchTerm={this.updateSearchTerm.bind(this)}
                  updateShowVerticalFilters={this.updateShowVerticalFilters.bind(this)}
                  onSelectAll={this.onSelectAll.bind(this)}
                  withCheckbox={withCheckbox}
                  withPagination={withPagination}
                  pageSize={pageSize}
                />
              </div>
              <div className="Table-grid">
                <Grid
                  {...this.state}
                  updateData={this.updateData.bind(this)}
                  updateSchema={this.updateSchema.bind(this)}
                  updateSortingList={this.updateSortingList.bind(this)}
                  updateFilterList={this.updateFilterList.bind(this)}
                  withCheckbox={withCheckbox}
                  onSelect={this.onSelect.bind(this)}
                  onSelectAll={this.onSelectAll.bind(this)}
                  showMenu={true}
                  type="data"
                  size="comfortable"
                  draggable={true}
                  withPagination={withPagination && totalPages > 1}
                  pageSize={pageSize}
                  loaderSchema={loaderSchema}
                />
              </div>
              {withPagination && (totalPages > 1) && (
                <div className="Table-pagination">
                  <Pagination
                    page={this.state.page}
                    totalPages={getTotalPages(totalRecords, pageSize)}
                    type="jump"
                    onPageChange={this.onPageChange.bind(this)}
                  />
                </div>
              )}
            </Card>
          </div>
          <div className={`Table-filters Table-filters--vertical${!showVerticalFilters ? ' d-none' : ''}`}>
            <div className="Table-filtersHeading">
              <Subheading>Filters</Subheading>
              <Icon name="close" className="Table-filtersCloseIcon" onClick={() => this.setState({ showVerticalFilters: false })} />
            </div>
            <div>
              <div className="Table-filter">
                <Dropdown
                  key="gender"
                  disabled={loading}
                  withCheckbox={true}
                  showApplyButton={true}
                  inlineLabel={"Gender"}
                  options={[
                    { label: 'Male', value: 'male', selected: true },
                    { label: 'Female', value: 'female', selected: true },
                  ]}
                  onChange={selected => this.onFilterChange("gender", selected)}
                />
              </div>
              <div className="Table-filter">
                <DatePicker
                  withInput={true}
                  label="Date"
                  inputOptions={{
                    placeholder: "mm/dd/yyyy",
                    disabled: loading,
                    minWidth: 'unset'
                  }}
                  onDateChange={(_date, dateStr) => this.onFilterChange("date", dateStr)}
                />
              </div>
            </div>
          </div>
        </div>
      );
    }
  }

  const translateData = (schema, data) => {
    let newData = data;

    if (schema.translate) {
      const translatedData = schema.translate(data);
      newData = {
        ...newData,
        [schema.name]: typeof translatedData === 'object' ? {
          ...newData[schema.name],
          ...translatedData
        } : translatedData
      };
    }
    if (typeof newData[schema.name] !== 'object') newData[schema.name] = { title: newData[schema.name] };

    return newData;
  }

  const onFilterChange = {
    "name": (a, filters) => {
      for (const filter of filters) {
        switch (filter) {
          case 'a-g':
            if (a.firstName[0].toLowerCase() >= 'a' && a.firstName[0].toLowerCase() <= 'g') return true;
            break;
          case 'h-r':
            if (a.firstName[0].toLowerCase() >= 'h' && a.firstName[0].toLowerCase() <= 'r') return true;
            break;
          case 's-z':
            if (a.firstName[0].toLowerCase() >= 's' && a.firstName[0].toLowerCase() <= 'z') return true;
            break;
        }
      }
      return false;
    },
    "gender": (a, filters) => {
      for (const filter of filters) {
        if (a.gender.toLowerCase() === filter) return true;
      }
      return false;
    }
  };

  const filterData = (data, filterList) => {
    let filteredData = data;
    if (filterList) {
      Object.keys(filterList).forEach(name => {
        const filters = filterList[name];
        const onChange = onFilterChange[name];
        if (onChange) {
          filteredData = filteredData.filter(d => onChange(d, filters));
        }
      });
    }

    return filteredData;
  };

  const sortData = (schema, data, sortingList) => {
    const sortedData = [...data];
    sortingList.forEach(l => {
      const sIndex = schema.findIndex(s => s.name === l.name);
      if (sIndex !== -1) {
        const defaultComparator = (a, b) => {
          const aData = translateData(schema[sIndex], a);
          const bData = translateData(schema[sIndex], b);
          return aData[l.name].title.localeCompare(bData[l.name].title);
        };

        const {
          comparator = defaultComparator
        } = schema[sIndex];

        sortedData.sort(comparator);
        if (l.type === 'desc') sortedData.reverse();
      }
    });

    return sortedData;
  };

  const paginateData = (data, page, pageSize) => {
    const start = (page - 1) * pageSize;
    const end = start + pageSize;
    const paginatedData = data.slice(start, end);
    return paginatedData;
  };

  const data = [
    {
        "firstName": "Brooke",
        "lastName": "Heeran",
        "email": "bheeran0@altervista.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Frazer",
        "lastName": "Cathro",
        "email": "fcathro1@ucla.edu",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lemmie",
        "lastName": "Ciric",
        "email": {
            "title": "lciric2@dmoz.org",
            "metaList": [
                "First",
                "Second"
            ]
        },
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Randy",
        "lastName": "Boatwright",
        "email": "rboatwright3@arstechnica.com",
        "status": "Completed",
        "gender": "Male"
    },
    {
        "firstName": "Rolando",
        "lastName": "Cyples",
        "email": "rcyples4@biglobe.ne.jp",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Lem",
        "lastName": "Males",
        "email": "lmales5@admin.ch",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Sayres",
        "lastName": "Adelberg",
        "email": "sadelberg6@uol.com.br",
        "gender": "Male",
        "status": "Completed"
    },
    {
        "firstName": "Murray",
        "lastName": "Bravington",
        "email": "mbravington7@drupal.org",
        "gender": "Male",
        "status": "Failed"
    },
    {
        "firstName": "Jena",
        "lastName": "Swatheridge",
        "email": "jswatheridge8@npr.org",
        "gender": "Female",
        "status": "Failed"
    },
    {
        "firstName": "Annabel",
        "lastName": "Nelsey",
        "email": "anelsey9@google.com",
        "gender": "Female",
        "status": "Completed"
    }
];

  const schema = [
    {
      name: 'name',
      displayName: 'Name',
      width: 300,
      resizable: true,
      separator: true,
      tooltip: true,
      translate: a => ({
        title: `${a.firstName} ${a.lastName}`,
        firstName: a.firstName,
        lastName: a.lastName
      }),
      cellType: 'AVATAR_WITH_TEXT',
    },
    {
      name: 'email',
      displayName: 'Email',
      width: 350,
      resizable: true,
      sorting: false,
      cellType: 'WITH_META_LIST'
    },
    {
      name: 'gender',
      displayName: 'Gender',
      width: 200,
      resizable: true,
      comparator: (a, b) => a.gender.localeCompare(b.gender),
      cellType: 'STATUS_HINT',
      translate: a => ({
        title: a.gender,
        statusAppearance: (a.gender === 'Female') ? 'alert' : 'success'
      }),
    },
    {
      name: 'icon',
      displayName: 'Icon',
      width: 100,
      resizable: true,
      align: 'center',
      cellType: 'ICON',
      translate: _ => ({
        icon: 'events'
      })
    },
    {
      name: 'customCell',
      displayName: 'Custom Cell',
      width: 200,
      resizable: true,
      separator: true,
      cellRenderer: (props) => {
        const {
          loading
        } = props;

        if (loading) return <></>;

        return (
          <Button appearance={'primary'}>Button</Button>
        );
      }
    },
  ];

  const fetchData = (options) => {
    const {
      page,
      pageSize,
      sortingList,
      filterList,
      searchTerm
    } = options;

    const onSearch = (d, searchTerm = '') => {
      return (
        d.firstName.toLowerCase().match(searchTerm.toLowerCase())
        || d.lastName.toLowerCase().match(searchTerm.toLowerCase())
      );

      return true;
    }

    const filteredData = filterData(data, filterList);
    const searchedData = filteredData.filter(d => onSearch(d, searchTerm));
    const sortedData = sortData(schema, searchedData, sortingList);

    if (page && pageSize) {
      return new Promise(resolve => {
        window.setTimeout(() => {
          const start = (page - 1) * pageSize;
          const end = start + pageSize;
          const slicedData = sortedData.slice(start, end);
          resolve({
            searchTerm,
            schema,
            count: sortedData.length,
            data: slicedData,
          });
        }, 2000);
      });
    }

    return new Promise(resolve => {
      window.setTimeout(() => {
        resolve({
          searchTerm,
          schema,
          count: sortedData.length,
          data: sortedData,
        });
      }, 2000);
    });
  }

  const loaderSchema = schema.filter(s => {
    const { name, displayName, width, separator, cellType, cellRenderer } = s;
    return {
      name, displayName, width, separator, cellType, cellRenderer
    };
  });

  return (
    <div className="bg-secondary-lightest">
      <Table
        loaderSchema={loaderSchema}
        fetchData={fetchData}
      />
    </div>
  );
}
```


#### Side Nav

```jsx
import { Collapsible, VerticalNav } from '@innovaccer/design-system';

() => {
  const menus = [
    {
      name: 'patient_360',
      label: 'Patient 360',
      icon: 'assignment_ind',
      link: '/patient360',
    },
    {
      name: 'care_management',
      label: 'Care Management and Resources',
      icon: 'forum',
      subMenu: [
        {
          name: 'care_management.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'care_management.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'episodes',
      label: 'Episodes',
      disabled: true,
      icon: 'airline_seat_flat_angled'
    },
    {
      name: 'risk',
      label: 'Risk',
      icon: 'favorite',
      subMenu: [
        {
          name: 'risk.timeline',
          label: 'Timeline',
          icon: 'events'
        },
        {
          name: 'risk.care_plans',
          label: 'Care Plans',
          icon: 'events'
        }
      ]
    },
    {
      name: 'claims',
      label: 'Claims',
      icon: 'receipt'
    },
    {
      name: 'profile',
      label: 'Profile',
      icon: 'account_circle'
    },
    {
      name: 'manula_entry',
      label: 'Manual Entry',
      icon: 'border_color'
    },
    {
      name: 'documents',
      label: 'Documents',
      icon: 'assignment'
    }
  ];

  const [expanded, setExpanded] = React.useState(false);
  const [active, setActive] = React.useState({
    name: 'care_management.timeline'
  });

  const onClickHandler = (menu) => {
    console.log('menu-clicked: ', menu);
    setActive(menu);
  };

  return (
    <div style={{ height: 'calc(80vh)', background: 'var(--secondary-lightest)' }}>
      <Collapsible expanded={expanded} onToggle={setExpanded}>
        <VerticalNav
          menus={menus}
          expanded={expanded}
          active={active}
          onClick={onClickHandler}
          hoverable={false}
        />
      </Collapsible>
    </div>
  );
}
```