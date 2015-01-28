# FMX.InterstitialAd.Android
Admob Interstitials Snippet Code Using The Android JNI In Delphi XE7 Firemonkey

Sample Usage:

type
  TForm1 = class(TForm)
    Button2: TButton;
    Memo1: TMemo;
    procedure Button2Click(Sender: TObject);
  private
    { Private declarations }
  public
    { Public declarations }
          IAdvertisment : TInterstitialAdvertisment;
  end;
 
var
  Form1: TForm1;
 
implementation
 
{$R *.fmx}
 
procedure onAdClosedEvent(pszData:String);
begin
  Form1.Memo1.Lines.add('onAdClosed');
end;
 
procedure onAdFailedToLoadEvent(pszData:String);
begin
  Form1.Memo1.Lines.add('onAdFailedToLoad');
end;
 
procedure onAdLeftApplicationEvent(pszData:String);
begin
  Form1.Memo1.Lines.add('onAdLeftApplication');
end;
 
procedure onAdOpenedEvent(pszData:String);
begin
  Form1.Memo1.Lines.add('onAdOpened');
end;
 
procedure onAdLoadedEvent(pszData:String);
begin
  Form1.Memo1.Lines.add('onAdLoaded');
end;
 
 
procedure TForm1.Button2Click(Sender: TObject);
begin
  IAdvertisment := TInterstitialAdvertisment.Create;
  IAdvertisment.SetOnCloseEvent(onAdClosedEvent);
  IAdvertisment.SetOnAdFailedToLoad(onAdFailedToLoadEvent);
  IAdvertisment.SetOnAdLeftApplication(onAdLeftApplicationEvent);
  IAdvertisment.SetOnAdOpened(onAdOpenedEvent);
  IAdvertisment.SetOnAdLoaded(onAdLoadedEvent);
  IAdvertisment.TestMode := True;
  IAdvertisment.SetAdUnitID('ca-app-pub-1543398996171627/8995432791');
  IAdvertisment.InitAdvertisment;
end;
 
end.
